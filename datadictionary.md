# Data Dictionary for RFM Analysis Dataset

## Column Descriptions

1. **Customer ID (ID_Cliente)**
   - **Description**: Unique identifier assigned to each customer.
   - **Data Type**: Integer or String (depending on ID structure).
   - **Example**: `111`
   - **Usage**: Used to link transactions to a specific customer and to aggregate transactional data per customer.

2. **Transaction Date (Data_Transacao)**
   - **Description**: The date on which a transaction occurred.
   - **Data Type**: Date
   - **Example**: `14/04/2023`
   - **Usage**: Used to calculate the recency of customer transactions.

3. **Transaction Value (Valor_Transacao)**
   - **Description**: The monetary amount of a transaction.
   - **Data Type**: Currency
   - **Example**: `R$ 545,06`
   - **Usage**: Used to calculate the total and average monetary value contributed by the customer.

4. **Recency (Recência)**
   - **Description**: Number of days since the customer's last transaction.
   - **Data Type**: Integer
   - **Example**: `393`
   - **Usage**: Used to assess how recently a customer has made a purchase, influencing the recency score.

5. **Frequency (Frequência)**
   - **Description**: Total number of transactions made by the customer over a defined period.
   - **Data Type**: Integer
   - **Example**: `7`
   - **Usage**: Used to measure how often a customer makes a purchase, influencing the frequency score.

6. **Total Value (Valor)**
   - **Description**: Total monetary value of all transactions made by the customer.
   - **Data Type**: Currency
   - **Example**: `R$ 4,920.35`
   - **Usage**: Sum of all transaction values for a customer, used to calculate the average ticket and monetary value score.

7. **Average Ticket (Ticket Médio)**
   - **Description**: Average monetary value of transactions per customer.
   - **Data Type**: Currency
   - **Example**: `R$ 702,91`
   - **Usage**: Helps in understanding the spending behavior per transaction of the customer.

8. **Recency Score (score_recência)**
   - **Description**: Score based on the recency of the customer's last purchase.
   - **Data Type**: Float
   - **Example**: `2.552`
   - **Usage**: Quantifies the recency of transactions to prioritize recent customers.

9. **Frequency Score (score_frequência)**
   - **Description**: Score based on the frequency of the customer's transactions.
   - **Data Type**: Float
   - **Example**: `8.004`
   - **Usage**: Quantifies transaction frequency to prioritize frequent customers.

10. **Monetary Value Score (score_valor)**
    - **Description**: Score based on the monetary value of the customer's transactions.
    - **Data Type**: Float
    - **Example**: `9.439`
    - **Usage**: Quantifies spending to prioritize higher value customers.

11. **RFM Sum (soma_rfm)**
    - **Description**: Sum of recency, frequency, and monetary scores.
    - **Data Type**: Float
    - **Example**: `19.995`
    - **Usage**: Aggregate score used to calculate overall customer value.

12. **RFM (rfm)**
    - **Description**: Calculated metric based on the RFM sum to categorize customers.
    - **Data Type**: Float
    - **Example**: `2.8960`
    - **Usage**: Provides a basis for segmenting customers into different RFM bands.

13. **RFM Score (rfm_score)**
    - **Description**: Rounded up RFM score used for final segmentation.
    - **Data Type**: Integer
    - **Example**: `3`
    - **Usage**: Used to segment customers based on the defined RFM score ranges.

14. **Segment (segmento)**
    - **Description**: Categorization of customers based on their RFM scores.
    - **Data Type**: String
    - **Example**: `Em Risco`
    - **Usage**: Used for targeted marketing and customer relationship management.

## Example Usage
This data dictionary serves as a reference for understanding each column used in the RFM analysis, facilitating effective data management and analysis for customer segmentation and marketing strategy development.

--- 

This structured explanation will help anyone using the dataset to fully understand the purpose and usage of each data point in the context of RFM analysis.
