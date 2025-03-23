# Introducetion of dbt(data build tool)
dbt (data build tool) as a tool that helps you clean, transform, and organize data inside a data warehouse
![alt text](https://github.com/Yaxin12/dbt_demo/tree/main/image/1.png)

### How dbt Works
Imagine you have a huge spreadsheet full of messy data—duplicate values, missing numbers, inconsistent formats. Before you can analyze it, you need to clean and organize it. dbt helps you do this automatically using SQL scripts.

### Key Features of dbt
1. Transforms Data – dbt takes raw data and cleans it up using SQL.

2. Organizes SQL Code – Instead of writing one big SQL query, you can break it into smaller, reusable parts.

3. Builds a DAG (Directed Acyclic Graph) – dbt automatically figures out which steps depend on each other and runs them in the right order.

4. Tests Data – dbt can check for errors, duplicates, or missing values before you use the data.

5. Documents Everything – It creates reports to explain how data is transformed.

### Why Use dbt?
* It saves time by automating repetitive SQL tasks.

* It improves teamwork because different people can collaborate on SQL models.

* It makes data pipelines more reliable with testing and documentation.
