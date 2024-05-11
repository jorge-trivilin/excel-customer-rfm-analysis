# Excel Customer RFM Analysis Project

## Project Background

I fully recognize the robust capabilities that Python offers for conducting Recency, Frequency, Monetary (RFM) analysis. Python's powerful libraries can automate data handling, enable complex calculations, and utilize machine learning algorithms for sophisticated customer segmentation. 

But i was intrigued to explore the fundamentals of RFM analysis in a more hands-on and straightforward manner. This curiosity led me to undertake an RFM analysis project using Excel. The aim was to manually perform the segmentation process, providing an educational perspective on the basic mechanics of RFM without the aid of advanced programming techniques or machine learning algorithms. Even though this analysis will never work if we are creating a data product for production or when we are dealing with a high volume of data.

## Project Description

This Excel-based RFM Analysis Project is designed as an exploratory exercise to understand the core principles of customer segmentation based on their purchasing behavior. Using only Excel functions, the project focuses on calculating key metrics such as recency, frequency, and monetary values, and then scoring these metrics to segment customers into various categories. 

This manual approach in Excel serves several purposes:
- **Educational Insight**: It offers a clear view of how each component of RFM contributes to customer segmentation, highlighting the direct impact of different scoring strategies.
- **Simplicity**: It allows for the manipulation and visualization of data without the need for programming, making it accessible to users who might not be familiar with Python.
- **Basis for Comparison**: By performing RFM analysis in Excel, I can compare the outcomes with those derived from more complex systems, providing a baseline to appreciate the enhancements that machine learning and automation can bring to such analyses.

Through this project, I seek to demonstrate that while tools like Python provide scalability and depth, foundational data analysis techniques remain powerful when applied correctly, even within the constraints of simpler software like Excel.

---

This description not only showcases your knowledge of advanced analytical tools but also emphasizes your curiosity and methodical approach to understanding the foundational aspects of data analysis techniques.

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
