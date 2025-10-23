<div align="center">
  
[![GitHub](https://img.shields.io/badge/GitHub-%20?style=for-the-badge&logo=github&labelColor=black&color=blue)][1]
[![LinkedIn](https://img.shields.io/badge/LinkedIn-%20?style=for-the-badge&logo=linkedin&labelColor=0A66C2&color=blue)][2]

[1]: https://github.com/nicole-kutswa
[2]: https://www.linkedin.com/in/nicole-kutswa/ 

</div>

# <div align="center">Data Modeling Sales Data Using Power-Pivot</div>
<div align="center"><img src="https://github.com/nicole-kutswa/Data-modeling-With-Power-Pivot/blob/main/output/model.gif?raw=true"></div>



# Overview

**Data modeling** is the process of organizing and structuring data so that it becomes easy to store, relate, and analyze.  
It defines **what data exists**, **how it connects**, and **how it can be used to generate insights**.

In this project, I applied data modeling concepts using **Excel Power Pivot** to link multiple tables, create relationships, and perform advanced analysis efficiently.

---

# Why Data Modeling Matters
Data modeling helps to:
- Eliminate data redundancy and inconsistency  
- Create logical connections between datasets  
- Improve the speed and accuracy of analysis  
- Enable better visualization and reporting through PivotTables or dashboards 

## Dataset:
[customer table](customers.csv)<br>
[orders table](orders.csv)<br>
[products table](products.csv)

## Data Dictionary

### Customers Table
| Field | Description |
|--------|--------------|
| **Customer ID** | A unique identifier assigned to each customer. Used to link customer details to their orders. |
| **Customer Name** | The full name of the customer. |
| **Email** | Customer’s email address, used for communication or marketing purposes. |
| **Phone Number** | Customer’s contact phone number. |
| **Address Line 1** | The primary street address of the customer. |
| **City** | The city where the customer resides. |
| **Country** | The country where the customer is located. |
| **Post Code** | The postal or ZIP code associated with the customer’s address. |
| **Loyalty Card** | Indicates whether the customer is enrolled in a loyalty or rewards program (Yes/No). |

---

### Orders Table
| Field | Description |
|--------|--------------|
| **Order ID** | A unique identifier for each order placed. |
| **Order Date** | The date the order was placed or processed. |
| **Customer ID** | Identifier linking the order to the corresponding customer in the Customers table. |
| **Product ID** | Identifier linking the order to the specific product in the Products table. |
| **Quantity** | The number of product units ordered. |

---

### Products Table
| Field | Description |
|--------|--------------|
| **Product ID** | A unique identifier for each product offered. |
| **Coffee Type** | The specific coffee variety or blend (e.g., Arabica, Robusta, Espresso). |
| **Roast Type** | The roast level of the coffee beans (e.g., Light, Medium, Dark). |
| **Size** | The packaging or serving size of the product (e.g., 250g, 500g, 1kg). |
| **Unit Price** | The selling price per product unit. |
| **Price per 100g** | The standardized price of the coffee per 100 grams for comparison purposes. |
| **Profit** | The net profit earned per product unit sold (Unit Price minus cost). |

## Implementation:

### Data Preparation and Modeling Process

The dataset was first **loaded into Power Query in Excel** for cleaning and validation.  
In this stage, the following checks were performed:
- Ensured that all tables were **free from missing or duplicate records**.  
- Verified that data types (e.g., numbers, dates, and text fields) were **consistent and correctly formatted**.  
- Checked for any **errors or inconsistencies** in key columns such as *Customer ID*, *Product ID*, and *Order Date*.

After confirming the data quality, the cleaned tables were **loaded into the Excel Data Model (Power Pivot)**, where **relationships** were created between them:
- The **Customer ID** field linked the *Customers* table to the *Orders* table.  
- The **Product ID** field linked the *Products* table to the *Orders* table.  

These relationships enabled efficient data aggregation and analysis across multiple tables.

---

### Calculated Columns and Measures

#### Returning Customer Check  
A **calculated column** was added to the *Customers* table to identify whether each customer was a returning customer.  
This was achieved using the following DAX formula:
```DAX
Returning Customer = IF(
    CALCULATE(
        COUNTROWS(Orders),
        FILTER(Orders, Orders[Customer ID] = Customers[Customer ID])
    ) > 1,
    "Yes",
    "No"
)
Profit per Item = RELATED(Products[Profit]) * Orders[Quantity]
```
### Data Analysis and Visualization

After creating the calculated columns, a **PivotTable** was used to analyze and summarize the data.  
A **heatmap visualization** was applied to easily identify which **coffee type generated the highest profit**   
<img src ="https://github.com/nicole-kutswa/Data-modeling-With-Power-Pivot/blob/main/output/profit per coffee type.PNG?raw=true">

Next, a **Customer Summary PivotTable** was created to highlight:

- The **customers who generated the highest overall profit based on profit per unit**, and
<img src ="https://github.com/nicole-kutswa/Data-modeling-With-Power-Pivot/blob/main/output/returning customers.PNG?raw=true">

- The **most frequent (returning) customers based on the count of order ID**
<img src ="https://github.com/nicole-kutswa/Data-modeling-With-Power-Pivot/blob/main/output/returning customers2.PNG?raw=true">

Finally, a **line chart** was developed to visualize how different **coffee types performed over the years**, showing trends in sales and profitability.  
A **slicer based on Roast Type** was also added to allow interactive filtering, making it easier to compare performance across different roast categories.<br>
<img src ="https://github.com/nicole-kutswa/Data-modeling-With-Power-Pivot/blob/main/output/visualisation.PNG?raw=true"><br>


### About Me
#### Hi, I'm Nicole
I am a Data Engineer Enthusiast and  Data science & ML practitioner

[![GitHub](https://img.shields.io/badge/GitHub-%20?style=for-the-badge&logo=github&labelColor=black&color=blue)][1]
[![LinkedIn](https://img.shields.io/badge/LinkedIn-%20?style=for-the-badge&logo=linkedin&labelColor=0A66C2&color=blue)][2]

[1]: https://github.com/nicole-kutswa
[2]: https://www.linkedin.com/in/nicole-kutswa/


