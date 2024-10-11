# Oodles of Noodles - Data Analysis

🍜 **Dive into the world of noodle data!** This project centers around analyzing key performance indicators (KPIs) and sales trends for a popular noodle company, "Oodles of Noodles." The analysis includes sales data, customer segmentation, revenue distribution, and product performance, offering a deep dive into the company’s operations.

🔍 **Curious about the interactive dashboard used in this analysis?** You can explore the visualizations and insights in the Power BI file.

# Background

The "Oodles of Noodles" analysis was created to help the company improve its sales strategies, identify its top-selling products, and understand customer preferences across various regions. By leveraging the data, the company can focus on boosting sales, improving inventory management, and targeting the right customer segments.

### Key Questions Addressed:
1. **Which noodle products generate the highest revenue?**
2. **How do sales vary across different regions and customer segments?**
3. **What are the trends in revenue over time?**
4. **Which customer groups are the most profitable?**
5. **What is the distribution of sales across different noodle categories?**

# Tools I Used

For this project, the following tools were utilized:
- **Power BI:** The primary tool for creating interactive visualizations and conducting in-depth analysis.
- **DAX (Data Analysis Expressions):** Used for advanced calculations and creating dynamic metrics in the Power BI dashboard.
- **M Code (Power Query):** Used to clean and transform data before loading it into the data model.
- **Conditional Formatting:** Applied to highlight key metrics in the dashboard to easily identify important insights.

# The Analysis

### 1. Sales by Product
A detailed analysis of revenue and sales volume for each noodle product was conducted. The dashboard presents:
- Top-selling products by revenue.
- Sales trends over time for different noodle categories.
- Comparison of product performance across various regions.

### 2. Regional Sales Trends
We visualized how sales vary by region, allowing the company to identify which geographic areas contribute the most to overall revenue. The dashboard includes:
- Heat maps displaying sales by region.
- Bar charts comparing region-specific sales volume.
- KPIs showing growth trends in high-performing regions.

### 3. Customer Segmentation
Customer data was segmented to understand which groups are the most profitable. The dashboard breaks down:
- Customer demographics (age, gender, income level).
- Revenue contribution from different customer segments.
- Insights into customer purchasing behavior, helping the company tailor its marketing efforts.

### 4. Time-Based Sales Trends
To understand how sales change over time, we created time-based analyses showing:
- Monthly, quarterly, and yearly sales trends.
- Peak seasons for noodle sales.
- Revenue growth rates over time, highlighting strong and weak sales periods.

# DAX Code for Advanced Metrics
To enrich the analysis, the following **DAX** code was used:

- **Total Sales Measure**: This measure calculates the total sales across all regions and products:

```dax
Total Sales = SUM(Sales[Revenue])
```

- **Sales Growth YoY**: This DAX formula calculates the year-over-year sales growth:

```dax
Sales Growth YoY = 
VAR CurrentYear = YEAR(TODAY())
RETURN
    DIVIDE(
        SUMX(FILTER(Sales, Sales[Year] = CurrentYear), Sales[Revenue]) 
        - SUMX(FILTER(Sales, Sales[Year] = CurrentYear - 1), Sales[Revenue]), 
        SUMX(FILTER(Sales, Sales[Year] = CurrentYear - 1), Sales[Revenue])
    )
```

This calculation helps the company track sales growth over time and pinpoint years of significant change.

### Conditional Formatting
**Conditional Formatting** was applied to the revenue KPIs to highlight the highest and lowest sales regions:

- **Green** for high-performing regions with sales above 1M.
- **Red** for regions with declining sales below 500K.

```Power BI
In the KPI card, select the "Format" pane -> Conditional Formatting -> Based on the field value.
```

# Advanced Power BI Techniques

1. **Dynamic Segmentation with DAX**: We implemented a **dynamic segmentation** where customer segments can change based on specific filters like revenue range or product category. This segmentation allows for more precise targeting and marketing campaigns.

```dax
Dynamic Segmentation = 
SWITCH(
    TRUE(),
    [Revenue] > 500000, "High Value Customers",
    [Revenue] > 200000, "Mid Value Customers",
    "Low Value Customers"
)
```

This helps the company categorize customers dynamically based on their contribution to the overall revenue.

2. **What-If Parameters for Scenario Analysis**: A **What-If Parameter** was added to the dashboard, allowing users to simulate different price or sales volume changes and see the effect on overall revenue and profit.

```Power BI
Modeling -> New Parameter -> What-If Parameter -> Define Min, Max, and Increment
```

This enabled the business to perform real-time scenario analysis and predict the outcomes of different pricing or volume strategies.

# What I Learned

🧩 **Advanced DAX Techniques:** Mastered the use of calculated columns, measures, and dynamic filtering to create insightful metrics for the dashboard.

📊 **Interactive Visualizations:** Enhanced my ability to build intuitive dashboards that allow for drill-downs and dynamic filtering, providing users with multiple layers of data insights.

💡 **Customer & Product Analysis:** Learned how to leverage Power BI to quickly analyze large datasets and present actionable insights to drive business decisions.

# Conclusions

### Key Insights:
1. **Top Products:** The highest revenue-generating noodle products were identified, allowing the company to prioritize them in marketing and sales efforts.
2. **Regional Focus:** Sales performance varies significantly by region, with certain areas showing higher growth potential.
3. **Customer Segmentation:** Certain customer groups, such as high-income earners, contribute significantly to overall sales, suggesting that targeted marketing could yield higher returns.
4. **Scenario Planning:** The What-If parameter analysis provided critical insights into how changes in pricing or volume could impact future revenue.
5. **Seasonal Trends:** The analysis revealed clear sales peaks during specific times of the year, helping the company plan inventory and promotional strategies more effectively.
