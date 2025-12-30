# 🛍 E-Commerce Analytics Platform — Microsoft Fabric | ADLS | Lakehouse | Power BI

This project demonstrates a **complete modern data engineering pipeline** using:

- Azure ADLS Gen2  
- Microsoft Fabric (Lakehouse + Notebooks + Pipelines)  
- Medallion Architecture (Bronze → Silver → Gold)  
- Power BI reporting  

---

## 📌 Business Goal

Create a **360-degree customer analytics platform** combining:

✔ Orders  
✔ Payments  
✔ Support tickets  
✔ Web engagement  
✔ Customer profile  

and deliver insights in **Power BI**.

---

## 🧭 Solution Architecture

```mermaid
flowchart LR
    A[CSV Files in ADLS Gen2] --> B[Fabric Pipeline\nGet Metadata + ForEach + Copy]
    B --> C[Fabric Lakehouse Files / Bronze]
    C --> D[Spark Notebook\nBronze ➜ Silver Cleaning]
    D --> E[Delta Tables / Silver Layer]
    E --> F[Customer 360 / Gold Table]
    F --> G[Power BI Report]


📂 Repository Structure
ECOMMERCE_FABRIC_LAKEHOUSE/
│
├── docs/
│   └── architecture_diagram.png
│
├── notebooks/
│   └── bronze_silver_gold_notebook.ipynb
│
├── code.txt
├── DATASET.zip
└── README.md

🥇 Medallion Layers
🟤 Bronze — Raw Layer
📍 Stored in: Lakehouse /Files/Bronze/

⚪ Silver — Clean Layer
Tables:
silver_customers
silver_orders
silver_payments
silver_support
silver_web

🟡 Gold — Analytics Layer
gold_customer360

🚀 How To Use
1️⃣ Upload CSV files to ADLS Gen2
Example path:
adls/ecommerce/raw/*.csv

2️⃣ Create a Fabric Workspace + Lakehouse
Lakehouse name:
ecommerce_lakehouse

3️⃣ Create Fabric Pipeline
Activities used:
Get Metadata — list files
ForEach — iterate

Copy Data — ADLS → Lakehouse /Files/Bronze/

4️⃣ Run Notebook (Bronze → Silver → Gold)
Run the Spark code from:
code.txt

This loads Bronze → cleans to Silver → aggregates to Gold.

5️⃣ Build Power BI Report
Connect to:
Lakehouse → Tables → gold_customer360

Then build dashboards such as:
Sales trends
Payment breakdown
Customer engagement
Support trends

📊 Suggested Power BI Visuals
Sales by Date
Orders by Customer
Payments by Method
Support Issues Trend
Web Engagement Activity

🛠 Tech Stack
Azure ADLS Gen2
Microsoft Fabric (Lakehouse + Notebook + Pipelines)
PySpark
Delta Tables
Power BI

🙌 Author
End-to-end demo project built for Microsoft Fabric Data Engineering learning & showcase.