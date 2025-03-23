# **Introduction to dbt (Data Build Tool)**  
dbt (Data Build Tool) is a powerful tool that helps you clean, transform, and organize data inside a data warehouse. It allows data teams to write modular SQL queries, apply transformations, and manage dependencies efficiently.  

![dbt Workflow](https://github.com/Yaxin12/dbt_demo/blob/main/image/1.png)  

## **How dbt Works**  
Imagine you have a massive dataset filled with inconsistencies—duplicate values, missing entries, and formatting issues. Before you can analyze the data, it must be cleaned and structured. dbt automates this process using SQL scripts, making data transformation easier and more scalable.  

## **Key Features of dbt**  
- **🔄 Data Transformation** – Cleans and structures raw data using SQL.  
- **📂 Modular SQL Code** – Allows you to break down complex queries into reusable components.  
- **📊 DAG (Directed Acyclic Graph)** – Automatically determines dependencies and executes transformations in the correct order.  
- **✅ Data Testing** – Validates data integrity by checking for errors, duplicates, and missing values.  
- **📖 Documentation & Lineage Tracking** – Generates reports that explain how data is transformed.  

## **Why Use dbt?**  
✔ **Automates repetitive SQL tasks**, saving time and reducing errors.  
✔ **Enhances collaboration**, allowing teams to work together on SQL models.  
✔ **Ensures data reliability** through built-in testing and documentation.  

---

# **Connecting dbt Cloud (dbt Labs) with BigQuery**  

## **1. Set Up a Google Cloud Project**  
- Ensure you have a **Google Cloud project** with **BigQuery enabled**.  
- Locate your **Project ID** in the **Google Cloud Console**.  

## **2. Create a Service Account**  
1. Navigate to **Google Cloud Console** → **IAM & Admin** → **Service Accounts**.  
2. Click **Create Service Account** and enter a name (e.g., `dbt-bigquery-service-account`).  
3. Click **Create & Continue**.  
4. Assign the **BigQuery Admin** role (or a custom role with the required permissions).  
5. Click **Done**.  

## **3. Generate and Download JSON Key**  
1. Open the **Service Accounts** list and select your newly created account.  
2. Go to the **Keys** tab.  
3. Click **Add Key** → **Create new key**.  
4. Select **JSON format** and download the key file (this will be used to authenticate dbt).  

## **4. Configure dbt Cloud**  
1. Log in to [dbt Cloud](https://cloud.getdbt.com/).  
2. Navigate to **Account Settings** → **Projects** → **Create Project**.  
3. Under **Connection**, select **BigQuery**.  
4. Upload the **JSON key file** you downloaded earlier.  
5. Fill in the following details:  
   - **🆔 Project ID**: Your Google Cloud project ID.  
   - **📂 Dataset**: The dataset where dbt models will be created.  
   - **⚙️ Threads**: Default is **4** (adjust based on performance needs).  
   - **⏳ Timeout**: Default is **300 seconds**.  

## **5. Test and Save Connection**  
- Click **Test** to verify the connection.  
- If successful, click **Save**.  

## **6. Initialize Your dbt Project**  
- Once connected, create a **new dbt project**.  
- Start adding models and run commands like:  

```sh
dbt run
dbt test
