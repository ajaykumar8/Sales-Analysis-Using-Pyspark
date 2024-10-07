
# **Sales Orders Data Exploration Using PySpark**

---

## **Project Overview**

This project focuses on exploring and analyzing sales order data using **PySpark**. The goal is to process large datasets efficiently, gain insights into sales performance over multiple years, and visualize key business metrics. The project involves data ingestion, transformation, aggregation, and visualization of sales trends to solve common business problems such as revenue tracking, product performance analysis, and customer behavior analysis.

---

## **Business Problem Solved**

Many businesses struggle to gain actionable insights from large-scale sales data. They need to analyze historical data to:
- Track revenue growth and identify sales trends.
- Understand customer purchase behavior.
- Optimize product inventory based on sales performance.
- Predict future sales and improve decision-making for inventory, pricing, and marketing.

This project provides a data-driven approach to solving these problems by leveraging PySpark to handle large datasets, perform data transformations, and extract meaningful insights.

---

## **Key Findings and Insights**

### **1. Revenue Growth**
- The analysis demonstrates steady revenue growth over multiple years, with a peak in 2021.
- **Insight**: Visualizing yearly sales helps businesses identify strong and weak performance periods, aiding strategic decision-making.

### **2. Top-Selling Products**
- The project aggregates product sales data to reveal the most popular items in the sales orders.
- **Insight**: Businesses can focus on stocking and promoting high-selling products for increased profitability.

### **3. Customer Insights**
- By segmenting customer data, the analysis identifies high-value and repeat customers.
- **Insight**: This allows businesses to target key customers with personalized marketing, loyalty programs, and special promotions.

### **4. Seasonal Trends**
- The project introduces columns for **Year** and **Month** to analyze sales trends over time, identifying peak periods of sales activity.
- **Insight**: Businesses can adjust inventory levels and marketing strategies around high-demand periods, ensuring optimal stock levels and targeted promotions during peak sales months.

### **5. Efficient Data Processing**
- The notebook uses partitioning to store the data by year and month, enabling faster querying and efficient handling of large datasets.
- **Insight**: Data partitioning optimizes performance when querying specific time periods, which is crucial for businesses managing large volumes of sales data.

---

## **Project Objectives**

- Load and process large-scale sales order data using PySpark.
- Perform data transformation to create additional useful columns (e.g., Year, Month, First Name, Last Name).
- Group and aggregate data to analyze yearly sales trends, top-selling products, and customer behavior.
- Partition and save the transformed data for efficient storage and querying.
- Visualize the results using **matplotlib** and **seaborn** for insights into sales performance.

---

## **Dataset**

The dataset consists of sales orders data across multiple years. It includes fields such as:
- `SalesOrderNumber`: Unique identifier for each order.
- `SalesOrderLineNumber`: Line number for individual items in an order.
- `OrderDate`: Date the order was placed.
- `CustomerName`: Full name of the customer.
- `Email`: Customer’s email address.
- `Item`: Product name.
- `Quantity`: Quantity sold.
- `UnitPrice`: Price per unit.
- `Tax`: Tax amount applied.

The dataset is stored as CSV files for each year in the directory `Files/orders/`.

---

## **Technical Details**

### **Data Ingestion**
- CSV files are loaded into a PySpark DataFrame.
- The schema is enforced using `StructType` to specify data types for each column.

### **Data Transformation**
- Additional columns are created:
  - **Year** and **Month** from the `OrderDate` column.
  - **First Name** and **Last Name** from splitting the `CustomerName`.
- Data is filtered and reorganized to prepare it for analysis.

### **Data Aggregation**
- The project aggregates data by grouping the sales orders by:
  - **Item**: To calculate total quantity sold per product.
  - **Year**: To sum up the gross revenue per year.
- PySpark's `groupBy` and `sum` functions are used for efficient aggregation.

### **Data Partitioning**
- The transformed data is saved as parquet files, partitioned by `Year` and `Month` for optimized storage and retrieval.

### **Visualization**
- Several visualizations are included:
  - **Bar Plot of Revenue by Year**: Displays total revenue generated per year.
  - **Pie Chart of Orders per Year**: Shows the distribution of sales orders across different years.
  - **Line Plot of Gross Revenue**: Illustrates revenue trends over the years.

### **Visualizations Implemented**:
- Bar plot of yearly revenue.
- Line chart displaying trends in revenue.
- Pie chart showcasing order distribution by year.

---

## **Tools and Technologies Used**

- **PySpark**: Used for data ingestion, transformation, and aggregation of large datasets.
- **Matplotlib**: For generating visualizations like bar plots and line charts.
- **Seaborn**: Used for advanced plotting and aesthetics in line plots.
- **Pandas**: DataFrames are converted to Pandas for visualization with `matplotlib`.
- **SQL**: Spark SQL is used to run SQL queries directly on Spark DataFrames for data analysis.
- **Parquet**: The dataset is stored as Parquet files for efficient querying and partitioning.

---

## **Setup Instructions**

### **1. Prerequisites**
- **PySpark**: Ensure you have PySpark installed in your environment. You can install it using:
  ```bash
  pip install pyspark
  ```
- **Matplotlib** and **Seaborn**: Required for data visualization. You can install them with:
  ```bash
  pip install matplotlib seaborn
  ```

### **2. Running the Notebook**
1. Clone the repository and place the dataset files under `Files/orders/`.
2. Open the Jupyter notebook and run the cells sequentially.
3. Ensure your environment is configured to support PySpark for processing the large dataset.

### **3. Data Files**
The project assumes the CSV files containing sales data are placed in the `Files/orders/` directory. The output files (transformed and partitioned data) will be saved in the `Files/transformed_data/` and `Files/partitioned_data/` directories.

---

## **Folder Structure**
```
- Files/
    - orders/
        - 2019.csv
        - 2020.csv
        - 2021.csv
    - transformed_data/
    - partitioned_data/
```

---

## **Potential Future Enhancements**
- **Predictive Analytics**: Add forecasting models to predict future sales based on historical data.
- **Customer Segmentation**: Implement clustering algorithms to segment customers based on their purchase patterns.
- **Interactive Dashboards**: Integrate with Plotly or Dash for interactive visualizations and dashboards.
- **Advanced Optimizations**: Further optimize performance using Spark caching or broadcasting for very large datasets.

---

## **Contact Information**
For any questions or suggestions, feel free to reach out to **[Ajay Kumar](mailto:ajay97kumarr@gmail.com)**.

---

This README provides a detailed overview of the project, including its objectives, the business problem it solves, key findings, and how to run the notebook. 
