# Amazon Power BI Dashboard

<div align="center">
    <img src="https://cdn.freebiesupply.com/logos/large/2x/amazon-dark-logo-svg-vector.svg" width="500px">
</div>

## Introduction:
**Amazon.com, Inc.**, also known simply as Amazon, is a leading American multinational technology company engaged in e-commerce, cloud computing, digital streaming, and artificial intelligence. For detailed information, visit [Wikipedia](https://en.wikipedia.org/wiki/Amazon_(company)).

## Project Objective 🎯:
This project aims to create a dynamic sales dashboard for Amazon's extensive product dataset. The dashboard will help visualize and analyze key metrics to drive strategic business decisions.

### Key performance indicators include 🔑:
| Objective                        | Description                                                   |
|----------------------------------|---------------------------------------------------------------|
| **Total Revenue**                | Track all income generated from sales.                        |
| **Total Orders**                 | Count of all completed sales transactions.                    |
| **Total Profit**                 | Net income after all expenses.                                |
| **Total Products**               | Number of unique products sold.                               |
| **Revenue by Date**              | Income distribution over a specific timeframe.                |
| **Top 5 Subcategories by Revenue** | Best performing categories.                                  |
| **Delivery Insights**            | Analysis of delivery timeframes.                              |


## Tools and Skills Used 🛠️:

## Tools and Skills Used 🛠️

<table>
    <tr>
        <!-- Specify width for each cell to ensure equal column width -->
        <td align="center" width="33%"><img alt="Power BI" width="35px" src="https://upload.wikimedia.org/wikipedia/commons/c/cf/New_Power_BI_Logo.svg"/><br>Microsoft Power BI</td>
        <td align="center" width="33%"><img alt="Excel" width="35px" src="https://cdn.worldvectorlogo.com/logos/excel-4.svg"/><br>Microsoft Excel</td>
        <td align="center" width="33%"><img alt="DAX" width="35px" src="https://upload.wikimedia.org/wikipedia/commons/c/cf/New_Power_BI_Logo.svg"/><br>DAX</td>
    </tr>
</table>

## DAX and Data Modeling Details 📈:

### Calendar Table Creation

Since a well-structured calendar table is the backbone of effective time-series analysis in any dashboard, I set up the calendar table using DAX:

- **Creating the Calendar Table:**
   ```plaintext
   Calendar = CALENDERAUTO()
   ```
   This function generates a calendar table containing a column of date values automatically derived from the data model.

- **Adding Year, Month, Quarter, and Day Columns:**
   ```plaintext
   Year = YEAR('Calendar'[Date])
   Month = FORMAT('Calendar'[Date], "MMM")
   Quarter = "Q" & QUARTER('Calendar'[Date])  // Corrected after fixing initial error
   Day = FORMAT('Calendar'[Date], "DDD")
   ```

- **Defining Week Type:**
   ```plaintext
   <Weektype = IF('Calendar'[Day] = "Sun" || 'Calendar'[Day] = "Sat", "Weekend", "Weekday")
   ```
   This categorization aids in filtering and analysis based on typical business cycles.

### Data Modeling

After setting up the calendar table, I established relationships within the data model to enable comprehensive time-series analysis.

- **Linking E-commerce and Calendar Tables:**
   The `OrderDate` column from the e-commerce table was used as the primary key to establish a relationship with the `Date` column of the calendar table.

   This step ensures that all data points are properly aligned with the time dimensions, allowing for dynamic time-based analyses and visualizations.

`
## Challenges Faced 😵:

While developing the Amazon Sales Dashboard, I encountered several hurdles that put my technical and problem-solving abilities to the test. The major ones I addressed are:

- **Understanding and DAX Function Syntax**: The journey began with the Calendar table, specifically when I tried to add a Quarter column. My initial attempt used the formula:
  ```
  Quarter = 'QUARTER('Calendar'[Date])'
  ```
  But, this quickly resulted in an error. It turned out that I needed to improve my formatting skills. After digging through forums and testing various expressions, I came up with the correct formula:
  ```
  Quarter = "Q" & QUARTER('Calendar'[Date])
  ```
  This challenge was a great exercise in the importance of syntax precision in DAX and pushed me to deepen my understanding of function contexts.

- **Data Modeling Nuances**: Aligning the e-commerce table with the Calendar table seemed straightforward—until I faced inconsistencies in date formats and missing entries. To ensure strong linkage, the solution called for meticulous data cleansing and format standardization. 

- **Creating Dynamic Visualizations**: One of the most exciting yet challenging aspects was developing visualizations that could dynamically adjust based on user interactions. Learning advanced functionalities in Power BI to ensure the visualizations were responsive as well as intuitive and insightful involved a lot of trial and error, but it was incredibly rewarding.

## Dashboard 📊:

![Amazon Dashboard](https://github.com/sanidhya-mitra/sanidhya-mitra/blob/main/Amazon_Dashboard.gif)

## Conclusion and Insights 💡:

The Amazon Dashboard provided crucial insights into the company's performance, highlighting significant growth and trends within the company's operations. Here are some key findings from the data visualized through the dashboard:

- **Total Revenue and Profit**: The dashboard reported a substantial total revenue of 13 million, with a profit of 7 million. This indicates a strong profit margin and robust sales mechanisms.

- **Total Orders and Products**: Over the period analyzed, Amazon processed a total of 10,543 orders involving 44 different products, demonstrating the diversity and scale of Amazon's operations.

- **Delivery Insights**: Delivery performance varied with 47,000 products delivered in over 10 days, 1,950 within 10 days, and 389,000 impressively within 5 days, showcasing efficient logistics for the majority of orders.

- **Revenue by Date**: There was a significant increase in revenue from $1.8 million in 2019 to $3.8 million in 2020, illustrating rapid growth and increased market penetration.

| Rank | Subcategory                   | Revenue   |
|------|-------------------------------|-----------|
| 1    | **Vitamins and Supplements**  | $1.516 million |
| 2    | **Men's Fashion**             | $1.154 million |
| 3    | **Medical Supplies and Equipment** | $1.091 million |
| 4    | **Boy's Fashion**             | $970k     |
| 5    | **Women's Fashion**           | $930k     |


These findings reflect Amazon's effective market strategies and operational excellence. The varied performance across different product subcategories and the efficiency in delivery systems highlight areas of strength and opportunities for further improvement.

---
<div align="center">
Thank you for taking the time to explore the Amazon Sales Dashboard project! Your interest and feedback are invaluable to me. I greatly appreciate your interest.
Feel free to reach out for any questions or suggestions about this project. I'm open to discussions and eager to assist. Connect with me on <a href="https://www.linkedin.com/in/sanidhya-mitra">LinkedIn | Sanidhya Mitra</a> <br>
Don't forget to follow and star ⭐ the repository if you find it valuable.
</div>

