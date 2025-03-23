# Introducetion of dbt(data build tool)
dbt (data build tool) as a tool that helps you clean, transform, and organize data inside a data warehouse
![alt text](https://github.com/Yaxin12/dbt_demo/blob/main/image/1.png)

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

# Connect dbt Cloud (dbt Labs) with BigQuery

### Set Up a Google Cloud Project
* Ensure you have a Google Cloud project with BigQuery enabled.

* Note your Project ID (found in Google Cloud Console).

### Create a Service Account
* Go to the Google Cloud Console → Navigate to IAM & Admin → Service Accounts.

* Click Create Service Account.

* Give it a name, e.g., dbt-bigquery-service-account.

* Click Create & Continue.

* Assign the BigQuery Admin role (or custom roles with necessary permissions).

* Click Done.

### Generate and Download JSON Key
* In the Service Accounts list, select the service account you just created.

* Go to the "Keys" tab.

* Click Add Key → Create new key.

* Choose JSON format, then Download the key file (it will be used to authenticate dbt).

### Set Up dbt Cloud Connection
* Log in to dbt Cloud (https://cloud.getdbt.com/).

* Navigate to Account Settings → Projects → Create Project.

* Under "Connection", select BigQuery.

* Upload the JSON key file you downloaded earlier.

* Fill in:

    * Project ID: Your Google Cloud project ID.

    * Dataset: Specify the dataset where dbt models will be created.

    * Threads: Default is 4 (adjust based on your use case).

    * Timeout: Default is 300 seconds.

### Test and Save Connection
* Click Test to verify the connection.

* If successful, click Save.

### Initialize dbt Project
* Once connected, create a new dbt project.

* You can start adding models and running dbt run, dbt test, etc.

### Run dbt Commands
* Use the dbt Cloud IDE or set up a CI/CD pipeline.

* Run dbt run to execute transformations in BigQuery.