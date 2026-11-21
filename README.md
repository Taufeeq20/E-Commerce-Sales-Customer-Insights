# E-Commerce-Sales-Customer-Insights
Interactive E-Commerce Sales and Customer Insights Dashboard using Power BI

The main purpose of this project is to analyse e-commerce business data and convert raw data into meaningful business insights using data analytics and business intelligence techniques.

In this project, I analyse sales performance, customer behaviour, product categories, payment methods, order status, delivery-related charges and customer satisfaction.

I developed an interactive, three-page Power BI dashboard to help users understand business performance through KPIs, charts and filters.

## Slide 2 – Problem Statement

E-commerce businesses generate large amounts of data from customer orders, products, payments, sellers and reviews.

However, analysing these different datasets separately can make it difficult to understand overall business performance.

Businesses may face challenges such as:

- Identifying sales trends over time.
- Understanding which product categories generate more sales.
- Monitoring order status and payment preferences.
- Analysing freight charges.
- Understanding customer distribution and repeat purchasing behaviour.
- Measuring customer satisfaction through reviews.

To address these analytical challenges, I developed an interactive dashboard that combines different datasets and presents important information in a visual format.

## Slide 3 – Project Objectives

The main objectives of my project are:

1. To analyse overall e-commerce sales performance.
2. To identify monthly sales and order trends.
3. To compare sales across product categories.
4. To understand customer payment preferences.
5. To analyse different order statuses.
6. To examine freight charges across product categories.
7. To understand customer distribution by state.
8. To analyse customer review scores.
9. To identify repeat and one-time customers.

These objectives help transform raw transactional data into useful information for business analysis.

## Slide 4 – Dataset Description

For this project, I used the **Brazilian E-Commerce Public Dataset by Olist**, available on Kaggle.

It is a real-world e-commerce marketplace dataset containing information about customers, orders, products, sellers, payments and customer reviews.

The dataset contains nine CSV files.

### Explanation of the nine dataset tables

**1. Customers**

This table contains customer information, including:

- Customer ID
- Unique customer ID
- ZIP code prefix
- City
- State

I used this table to analyse customer distribution by location and customer counts.

**2. Orders**

This table contains order-related information, including:

- Order ID
- Customer ID
- Order status
- Purchase timestamp
- Approval timestamp
- Carrier delivery date
- Customer delivery date
- Estimated delivery date

I used it to analyse order status, monthly trends and order performance.

**3. Order Items**

This table contains product details associated with each order, including:

- Order ID
- Order item ID
- Product ID
- Seller ID
- Shipping limit date
- Price
- Freight value

I used this table to analyse product sales and freight charges.

**4. Products**

This table contains product information, including:

- Product ID
- Product category
- Product name length
- Product description length
- Number of product photos
- Product weight
- Product dimensions

I used it to analyse sales across product categories.

**5. Sellers**

This table contains seller information, including:

- Seller ID
- ZIP code prefix
- City
- State

It helps identify seller-related information in the marketplace dataset.

**6. Order Payments**

This table contains payment information, including:

- Order ID
- Payment sequence
- Payment type
- Number of instalments
- Payment value

I used it to analyse payment methods and payment-related information.

**7. Order Reviews**

This table contains customer feedback information, including:

- Review ID
- Order ID
- Review score
- Review comment title
- Review comment message
- Review creation date
- Review answer timestamp

I used it to analyse customer satisfaction through review scores.

**8. Geolocation**

This table contains geographical information, including:

- ZIP code prefix
- Latitude
- Longitude
- City
- State

It provides geographical reference information for locations in Brazil.

**9. Category Translation**

This table maps Portuguese product category names to English category names.

I used it to display product categories in English in the dashboard.

**Dataset summary:**

The dataset contains approximately 100,000 orders and multiple related tables. Each table provides a different part of the e-commerce business information.

## Slide 5 – Tools and Technologies

I worked with the following technologies as part of the analytics workflow:

**Power BI:** Used to create interactive dashboards, KPI cards, charts and filters.

**Power Query:** Used for data cleaning and transformation.

**DAX:** Used to create calculated measures and business KPIs.

**Excel:** Useful for inspecting and reviewing tabular data.

**SQL:** Useful for querying, filtering and analysing structured data.

**Tableau:** An additional business intelligence tool for developing visual analytics, if included in the completed project.

The main dashboard presented in this project was developed using Power BI.

## Slide 6 – Data Cleaning and Transformation

Before creating the dashboard, I prepared the raw datasets using Power Query.

The main data preparation activities included:

1. **Understanding the data:** I checked the number of rows, columns and data types in each table.
2. **Handling missing values:** I inspected null values and retained meaningful missing dates and comments instead of replacing them with incorrect values.
3. **Removing duplicates:** I checked duplicate records and removed exact duplicate rows where appropriate, particularly in the geolocation table.
4. **Trim:** I used Trim to remove unnecessary spaces at the beginning and end of text values.
5. **Clean:** I used Clean to remove unwanted non-printable characters.
6. **Changing data types:** I assigned appropriate types such as Text, Whole Number, Decimal Number and Date/Time.
7. **Checking ID columns:** I checked important identifiers to ensure they were suitable for creating relationships.

These steps helped improve data quality and prepare the tables for analysis.

## Slide 7 – Data Modelling

After cleaning the datasets, I created relationships between the tables in Power BI Model View.

I used one-to-many relationships for the main data model.

The important relationships include:

- Customers to Orders using Customer ID.
- Orders to Order Items using Order ID.
- Orders to Order Payments using Order ID.
- Orders to Order Reviews using Order ID.
- Products to Order Items using Product ID.
- Sellers to Order Items using Seller ID.
- Category Translation to Products using Product Category Name.

The one side contains unique values, while the many side can contain repeated values.

For example, one customer can place multiple orders, and one order can contain multiple order items.

I kept the Geolocation table separate because a ZIP code prefix can have multiple geographical records. This avoids creating an unreliable relationship.

Data modelling allows information from different tables to be analysed together in Power BI.

## Slide 8 – DAX Measures and KPI Calculations

After creating the data model, I developed DAX measures to calculate important business metrics.

The main measures are:

**1. Total Sales**

Calculates the sum of product item prices.

It helps measure the total value of the items sold. It does not represent profit.

**2. Total Orders**

Calculates the distinct number of orders.

It helps monitor the overall order volume.

**3. Total Customers**

Calculates the distinct number of unique customers using the customer unique ID.

It helps understand the customer base.

**4. Total Products Sold**

Counts the rows in the Order Items table.

It represents the number of order-item records, not necessarily the number of distinct products.

**5. Total Freight**

Calculates the sum of freight charges.

It helps analyse shipping-related charges.

**6. Average Order Value**

Calculates Total Sales divided by Total Orders.

It represents the average product sales value per order.

**7. Average Review Score**

Calculates the average customer review score.

It helps measure customer satisfaction.

**8. Total Reviews**

Counts the review records.

It helps understand the volume of customer feedback.

These DAX measures are used in KPI cards and charts throughout the dashboard.

## Slide 9 – Dashboard Page 1: Sales Overview

Now I will explain the first page of my Power BI dashboard, called **Sales Overview**.

This page provides an overall view of the e-commerce business performance.

### KPI Cards

At the top, I created four KPI cards.

**Total Sales:** Shows the total value of product items sold.

**Total Orders:** Shows the total number of distinct orders.

**Total Customers:** Shows the number of unique customers.

**Total Products Sold:** Shows the number of order-item records.

These cards help users understand the overall business performance quickly.

### Chart 1 – Monthly Sales Trend

This is a line chart.

The X-axis represents the month, and the Y-axis represents total sales.

The purpose of this chart is to understand how sales change over time.

It helps identify:

- Months with higher sales.
- Months with lower sales.
- Seasonal patterns.
- Changes in sales performance.

For example, if sales increase during a particular month, the business can investigate the reasons behind that increase.

### Chart 2 – Sales by Product Category

This is a clustered bar chart.

The category names are displayed on the Y-axis, and total sales are displayed on the X-axis.

It compares the sales contribution of different product categories.

It helps identify:

- Categories generating higher sales.
- Categories generating lower sales.
- Product categories that may need more attention.

Businesses can use this information when planning product promotions and inventory.

### Chart 3 – Orders by Payment Type

This is a donut chart.

The payment types are displayed as segments, and the values represent the number of distinct orders associated with each payment type.

It helps understand customer payment preferences.

For example, businesses can identify which payment methods are more commonly used and plan their payment services accordingly.

### Chart 4 – Average Review Score by Product Category

This is a clustered column chart.

The X-axis represents product categories, and the Y-axis represents the average review score.

It helps compare customer ratings across product categories.

A higher average score indicates better customer feedback, while a lower score may indicate areas that need improvement.

### Chart 5 – Monthly Order Count

This is a line chart.

The X-axis represents the month, and the Y-axis represents the number of distinct orders.

It shows how order volume changes over time.

This chart is different from the Monthly Sales Trend because sales value and order volume are not the same.

For example, sales value may increase even when the number of orders remains stable.

### Slicers

I added two slicers:

**Year:** Allows users to filter the dashboard by purchase year.

**State:** Allows users to filter the dashboard by customer state.

These slicers make the dashboard interactive and allow users to explore specific periods and locations.

## Slide 10 – Dashboard Page 2: Order and Product Analysis

The second page is called **Order and Product Analysis**.

This page focuses on order performance, product categories, freight charges and customer locations.

### Chart 1 – Orders by Order Status

This is a donut chart.

The order status is displayed as the category, and the values represent the number of distinct orders.

It shows how orders are distributed across different statuses, such as delivered, shipped, canceled and unavailable.

It helps businesses monitor order completion and identify statuses that may require further investigation.

### Chart 2 – Top 10 Product Categories by Orders

This is a clustered bar chart.

The Y-axis displays product categories, and the X-axis displays the number of distinct orders containing those categories.

I applied a Top 10 filter to display the ten categories with the highest order counts.

It helps identify the product categories that appear most frequently in customer orders.

Businesses can use this information for product planning and inventory decisions.

### Chart 3 – Freight Value by Product Category

This is a clustered bar chart.

The Y-axis represents product categories, and the X-axis represents total freight value.

It compares freight charges across different product categories.

It helps identify categories associated with higher total shipping charges.

Businesses can investigate shipping costs and evaluate logistics performance.

### Chart 4 – Average Order Value by Payment Type

This is a clustered column chart.

The X-axis represents payment types, and the Y-axis represents average order value.

It is intended to compare the average order value across payment methods.

It helps investigate whether order values differ according to payment type.

The calculation should be validated at order level because an order can have multiple payment records and multiple order items.

### Chart 5 – Orders by Customer State

This is a clustered bar chart.

The Y-axis represents customer states, and the X-axis represents the number of distinct orders.

It shows the geographical distribution of orders across Brazilian states.

Businesses can use this information to identify regions with higher order activity and plan regional marketing and delivery operations.

### Slicers

I added Year and Payment Type filters to allow users to explore order and payment information interactively.

## Slide 11 – Dashboard Page 3: Customer Insights

The third page is called **Customer Insights**.

This page focuses on customer distribution, customer satisfaction and purchasing behaviour.

### KPI Cards

I created three KPI cards.

**Total Customers:** Shows the number of unique customers.

**Average Review Score:** Shows the average rating provided by customers.

**Total Reviews:** Shows the total number of review records.

These KPIs provide a quick overview of customer activity and feedback.

### Chart 1 – Customer Distribution by State

This is a clustered bar chart.

The Y-axis represents customer states, and the X-axis represents the number of unique customers.

It helps identify the states with higher and lower customer counts.

Businesses can use this information to understand their customer distribution and plan regional marketing strategies.

### Chart 2 – Customer Review Score Distribution

This is a clustered column chart.

The X-axis represents review scores from 1 to 5, and the Y-axis represents the number of reviews.

It shows how customers have rated their shopping experience.

For example:

- A score of 1 represents a very low rating.
- A score of 5 represents a very high rating.

This chart helps businesses understand customer satisfaction and identify whether negative feedback needs attention.

### Chart 3 – Repeat vs One-Time Customers

This is a donut chart.

It divides customers into two groups:

**Repeat Customers:** Customers who have placed more than one order.

**One-Time Customers:** Customers who have placed exactly one order.

The chart helps understand customer purchasing behaviour and repeat purchasing activity.

Businesses can use this information to plan customer retention strategies, loyalty programmes and promotional campaigns.

The repeat-customer calculation groups orders by unique customer identity, so the measure should be validated against the customer-level data before presenting exact figures.

## Slide 12 – Business Insights

The dashboard helps businesses explore several important areas.

**Sales Performance:** Monthly sales trends help businesses understand changes in sales over time.

**Product Performance:** Category-wise sales and order charts help identify product categories with higher sales or order activity.

**Payment Preferences:** Payment analysis helps businesses understand the payment methods used by customers.

**Order Performance:** Order status analysis helps monitor completed, canceled and other order statuses.

**Logistics Analysis:** Freight analysis helps compare shipping charges across product categories.

**Customer Analysis:** State-wise customer distribution helps identify important customer locations.

**Customer Satisfaction:** Review scores help businesses understand customer feedback.

**Customer Retention:** Repeat versus one-time customer analysis helps evaluate repeat purchasing behaviour.

These are analytical insights that can support business decisions. The actual findings should be explained using the values and patterns shown in the dashboard.

## Slide 13 – Conclusion

To conclude, I successfully developed an interactive E-Commerce Sales and Customer Insights Dashboard using Power BI.

During this project, I worked with multiple related datasets and performed data cleaning, transformation, data modelling and DAX calculations.

I created three dashboard pages covering:

1. Sales Overview
2. Order and Product Analysis
3. Customer Insights

The project helped me understand how raw business data can be transformed into meaningful visual information.

I also improved my practical knowledge of Power Query, data modelling, DAX and Power BI visualisation.

This project demonstrates my ability to work with real-world datasets and develop interactive dashboards for business analysis.

**Thank you.**
