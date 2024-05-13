# Amazon Sales Dashboard

<div align="center">
    <img src="https://cdn.freebiesupply.com/logos/large/2x/amazon-dark-logo-svg-vector.svg" width="500px">
</div>

## Introduction:
**Amazon.com, Inc.**, also known simply as Amazon, is a leading American multinational technology company engaged in e-commerce, cloud computing, digital streaming, and artificial intelligence. For detailed information, visit [Wikipedia](https://en.wikipedia.org/wiki/Amazon_(company)).

## Project Objective 🎯:
This project aims to create a dynamic sales dashboard for Amazon's extensive product dataset. The dashboard will help visualize and analyze key metrics to drive strategic business decisions.

### Key performance indicators include 🔑:
- **Total Revenue**: Track all income generated from sales.
- **Total Orders**: Count of all completed sales transactions.
- **Total Profit**: Net income after all expenses.
- **Total Products**: Number of unique products sold.
- **Revenue by Date**: Income distribution over a specific timeframe.
- **Top 5 Subcategories by Revenue**: Best performing categories.
- **Delivery Insights**: Analysis of delivery timeframes.

## Tools and Skills Used 🛠️:
- Microsoft Power BI
- Microsoft Excel
- DAX
- Dataset

## DAX and Data Modeling Details 📈:

### Calendar Table Creation

Since a well-structured calendar table is the backbone of effective time-series analysis in any dashboard, I set up the calendar table using DAX:

1. **Creating the Calendar Table:**
   ```plaintext
   Calendar = CALENDERAUTO()
   ```
   This function generates a calendar table containing a column of date values automatically derived from the data model.

2. **Adding Year, Month, Quarter, and Day Columns:**
   ```plaintext
   Year = YEAR('Calendar'[Date])
   Month = FORMAT('Calendar'[Date], "MMM")
   Quarter = "Q" & QUARTER('Calendar'[Date])  // Corrected after fixing initial error
   Day = FORMAT('Calendar'[Date], "DDD")
   ```

3. **Defining Week Type:**
   ```plaintext
   <Weektype = IF('Calendar'[Day] = "Sun" || 'Calendar'[Day] = "Sat", "Weekend", "Weekday")
   ```
   This categorization aids in filtering and analysis based on typical business cycles.

### Data Modeling

After setting up the calendar table, I established relationships within the data model to enable comprehensive time-series analysis.

- **Linking E-commerce and Calendar Tables:**
   The `OrderDate` column from the e-commerce table was used as the primary key to establish a relationship with the `Date` column of the calendar table.

   This step ensures that all data points are properly aligned with the time dimensions, allowing for dynamic time-based analyses and visualizations.

## Challenges Faced 😵:

Several challenges arose while developing the Amazon Sales Dashboard, putting technical and problem-solving abilities to the test. Here are some of the major issues I encountered and how I addressed them:

1. **Understanding and Correcting DAX Functions**: One of the first challenges I faced was during the creation of the Quarter column in our Calendar table. The initial formula I used was `Quarter = 'QUARTER('Calendar'[Date])'`, which resulted in an error. I observed the quarter could not be displayed correctly without additional text formatting. After researching and testing different formats, I corrected it to `Quarter = "Q" & QUARTER('Calendar'[Date])`. This improved my troubleshooting skills for DAX formulas.

2. **Calendar Table Alignment**: Initially aligning the e-commerce table with the Calendar table was more challenging than anticipated. The dates in the e-commerce table had inconsistencies, such as different formats and missing values, which disrupted the relationship between the tables. I had to standardize the date formats and clean up the missing or incorrect entries before I could finally link the tables.

4. **Dynamic Visualizations**: Creating dynamic visualizations that automatically adjust based on user selections (like different time frames or product categories) posed a significant challenge. It was harder than I anticipated. To do so, I needed to learn more advanced Power BI features to ensure that the visualizations were not only responsive, but also intuitive and informative. This required iterative testing and learning to best utilize DAX in visual layers.


## Dashboard 📊:

![Amazon Dashboard](https://github.com/sanidhya-mitra/sanidhya-mitra/blob/main/Amazon_Dashboard.gif)

## Conclusion and Insights 💡:

The Amazon Sales Dashboard provided crucial insights into the sales performance, highlighting significant growth and trends within the company's operations. Here are some key findings from the data visualized through the dashboard:

- **Total Revenue and Profit**: The dashboard reported a substantial total revenue of $13 million, with a profit of $7 million. This indicates a strong profit margin and robust sales mechanisms.

- **Total Orders and Products**: Over the period analyzed, Amazon processed a total of 10,543 orders involving 44 different products, demonstrating the diversity and scale of Amazon's operations.

- **Delivery Insights**: Delivery performance varied with 47,000 products delivered in over 10 days, 1,950 within 10 days, and 389,000 impressively within 5 days, showcasing efficient logistics for the majority of orders.

- **Revenue by Date**: There was a significant increase in revenue from $1.8 million in 2019 to $3.8 million in 2020, illustrating rapid growth and increased market penetration.

- **Top 5 Subcategories by Revenue**:
  1. **Vitamins and Supplements**: 1.516 million
  2. **Men's Fashion**: 1.154 million
  3. **Medical Supplies and Equipment**: 1.091 million
  4. **Boy's Fashion**: 970k
  5. **Women's Fashion**: 930k

These findings reflect Amazon's effective market strategies and operational excellence. The varied performance across different product subcategories and the efficiency in delivery systems highlight areas of strength and opportunities for further improvement.

---
<div align="center">
Thank you for taking the time to explore the Amazon Sales Dashboard project! Your interest and feedback are invaluable to me. I greatly appreciate your interest.
</div>

