# Excel Customer RFM Analysis Project

## Overview
*This Excel-based RFM Analysis Project aims to segment customers based on their purchasing behavior using the Recency, Frequency, and Monetary (RFM) model. By calculating scores for each of these aspects and summing them, we categorize customers into different segments to tailor marketing strategies effectively.*

![Version](https://img.shields.io/badge/version-1.0.0-blue)

### About The Creator

*This project was created by Jorge Trivilin.* 

*Connect with Jorge here:*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Jorge_Trivilin-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/jorgetrivilin/)
[![GitHub](https://img.shields.io/badge/GitHub-jorgetrivilin-lightgrey?style=flat&logo=github)](https://github.com/jorge-trivilin/)

## Data Description
The dataset includes the following columns:

- **Customer ID**: Unique identifier for the customer.
- **Transaction Date**: Date when the transaction occurred.
- **Transaction Value**: Monetary value of the transaction.
- **Recency**: Days since the last transaction.
- **Frequency**: Total number of transactions.
- **Total Value**: Total monetary value from the customer.
- **Average Ticket**: Average transaction value per customer.
- **Recency Score**: Calculated score based on recency.
- **Frequency Score**: Calculated score based on frequency.
- **Monetary Value Score**: Calculated score based on monetary value.
- **RFM Sum**: Sum of recency, frequency, and monetary scores.
- **RFM**: Weighted score calculated from the RFM sum.
- **RFM Score**: Categorized score based on predefined ranges.
- **Segment**: Customer segment derived from the RFM Score.

## Calculations

### Recency
```excel
=TODAY() - [@[Transaction Date]]
```

### Frequency
```excel
=COUNTIF(A:A, [@[Customer ID]])
```

### Monetary Value
```excel
=SUMIF(A:A, [@[Customer ID]], C:C)
```

### Average Ticket
```excel
=[@[Total Value]] / [@[Frequency]]
```

### Recency Score
```excel
=(1 - PERCENTRANK.INC(D:D, [@[Recency]], 4)) * 10
```

### Frequency Score
```excel
=PERCENTRANK.INC(E:E, [@[Frequency]], 4) * 10
```

### Monetary Value Score
```excel
=PERCENTRANK.INC(F:F, [@[Frequency]], 4) * 10
```

### RFM Sum
```excel
=SUM(H:H, I:I, J:J)
```

### RFM
```excel
=PERCENTRANK.INC(K:K, [@[RFM Sum]], 4) * 10
```

### RFM Score
```excel
=CEILING([@RFM], 0)
```

### Segment Selection
```excel
=XLOOKUP([@RFM Score], S:S, T:T, FALSE, 0, 1)
```

## Segments Reference

| RFM Score | Segment        |
|-----------|----------------|
| 10        | Champions      |
| 9         | VIP Plus       |
| 8         | VIPs           |
| 7-5       | Valuable       |
| 4-2       | At Risk        |
| 1-0       | Immediate Attention |

---

This README serves as a comprehensive guide to understanding and implementing RFM analysis using the provided Excel template. It includes descriptions of data fields, formulas for each metric calculation, and a segment reference table to categorize customers based on their RFM scores.
