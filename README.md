### 📊 FinSight: Enterprise Financial Analytics Platform

### End-to-End Modern Data Stack: SQL Server ➡️ Microsoft Fabric ➡️ Direct Lake Power BI

### 📌 Project Overview

**FinSight** is a production-ready, cloud-native data analytics solution engineered within the **Microsoft Fabric** ecosystem. The platform ingests, processes, and visualizes a high-velocity financial dataset comprising **15K transactions** totaling **रु 137.03M** in volume for the fiscal year. 

This project demonstrates a complete modern data pipeline lifecycle: extracting raw relational data from an **SQL database**, centralizing it within a unified **OneLake Data Lakehouse**, and serving real-time corporate KPIs via **Direct Lake mode** without traditional import refresh bottlenecks. 

### 🛠️ Architecture & Technical Stack

[ SQL Database Source ] 
          │ (Fabric Data Factory / Copy Activity)
          ▼
[ Fabric Lakehouse (OneLake) ] ──▶ [ Delta Parquet Tables ]
          │ (Direct Lake Connection)
          ▼
[ Power BI Semantic Model ] ──▶ [ Executive Dashboard ]

* **Data Source:** Relational **SQL Server** database hosting core transactional ledgers and client dimension tables.
* **Data Ingestion & Orchestration:** **Fabric Data Factory** pipelines utilizing Dataflows Gen2 and optimized Copy Activities.
* **Storage & Layering:** **Fabric Lakehouse (OneLake)** storing optimized, open-source **Delta Parquet** tables to maintain strict ACID compliance.
* **Reporting Layer:** **Power BI Service in Direct Lake Mode**, allowing the dashboard to read memory-cached Delta tables instantly, entirely removing scheduled import refresh latencies.

### 📋 Step-by-Step Implementation

### Step 1: SQL Relational Data Modeling & Source Management

Designed and managed a normalized relational database structure in the source SQL system. The core transaction schema handles the following structural metrics: 

* Trans_Id *(VARCHAR, Primary Key)*: Unique tracker (e.g., T00000002).
* Trans_Date *(DATE)*: Transaction timestamps.
* Trans_Status *(VARCHAR)*: Operational states (Success, Failed, Pending).
* Trans_Type *(VARCHAR)*: Product lines (Loan EMI, Deposit, Investment, Card Payment).
* Financial Metrics *(DECIMAL)*: Gross Total_Amount, processing Total_Fees, and compliance Total_Tax.
* Demographic Keys *(VARCHAR)*: Structural dimensions covering Gender, Customer_Segment, and State.

### Step 2: Ingestion & Orchestration via Fabric Data Factory

* Configured cloud data gateways to securely connect the source **SQL Server** database to the Microsoft Fabric web workspace.
* Built automated orchestration pipelines using **Fabric Data Factory Pipelines** to manage data ingestion schedules and reduce source transactional load.
* Utilized **Dataflows Gen2** to clean data types, filter out structural anomalies, and handle null parameters uniformly.

### Step 3: OneLake Lakehouse Architecture & Delta Conversion

* Landed the raw relational data tables directly into the **Fabric Lakehouse Files layer**.
* Converted staging structures into optimized **Delta Lake tables** to enable high-speed analytics queries and future-proof data time-travel features.
* Mapped star-schema relationships between the transactional fact tables and customer dimension tables to optimize memory structures.

### Step 4: Semantic Modeling & Direct Lake Reporting

* Configured the **Power BI Semantic Model** directly inside the web-based Fabric Workspace.
* Connected to the underlying Delta tables using **Direct Lake mode**, combining the extreme query performance of Import mode with the real-time access of DirectQuery.
* Authored dynamic **DAX measures** to compute complex operational KPIs on the fly (e.g., success rate percentages, rolling tax volumes).

### 🚀 Key Business Insights Uncovered

### 💰 Financial & Revenue Health

* **Total Volume Processed:** रु 137.03M across 15K entries, averaging **रु 9.11K per transaction**.
* **Revenue Generation:** Captured **रु 216.45K** in processing fees and tracked **रु 38.98K** in total compliance taxes.
* **Pipeline Health:** Exposed an **85.7% Transaction Success Rate** (रु 33.4K tax weight), leaving a 10.5% failure rate to target for systematic optimizations.

### 👥 Customer & Product Segmentation

* **Dominant Tiers:** The **Retail Customer segment** generated the vast majority of tax revenue at **रु 21K**, outperforming the Premium, SME, Corporate, and Wealth tiers combined.
* **Demographic Balance:** Revealed near-perfect equity in financial activity between genders, with **Females accounting for 50.5%** (रु 19.7K) and **Males at 49.5%** (रु 19.3K).
* **Product Performance:** **Loan EMIs** commanded the highest volume, capturing **रु 38.73M** across 3K interactions, followed by **Deposits** at **रु 21.13M**.

### 🖥️ Dashboard Interface & Features

<img width="1024" height="581" alt="1788932782901-0cb07d98-416f-4246-a57c-6bce503bc936_1" src="https://github.com/user-attachments/assets/56369644-19e2-4e2a-a1cd-cb75a10e4b02" />


The dashboard consists of two user-focused analytical pages designed to serve separate corporate roles: 

1. **Overview Analysis Page (Executive View):** Tracks macro-trends, including a *Total_Tax by Month* area chart showing distinct activity spikes in May and September, alongside interactive regional charts showing **Maharashtra** (रु 6.0K) as the top geographic market.
2. **Transactions View (Auditor Ledger):** A lightning-fast row-level ledger detailing exact execution windows (Trans_Id, Trans_Date) supported by a global left-anchored filter panel allowing instant slicing by **Year**, **Dynamic Metrics**, **Category**, and **Occupation**.

### 🎯 Connect With Me

I specialize in engineering modern data architectures that transform raw data assets into corporate decision tools. If you are looking for a Data Engineer or Business Intelligence Analyst proficient in **Microsoft Fabric, SQL, and advanced Power BI ecosystems**, let's connect! 

💼 **LinkedIn:** [linkedin.com/in/murali-m-32aa51136](https://www.linkedin.com/in/murali-m-32aa51136)
🖥️ **GitHub / Blog:** [github.com/MuraliM1994](https://github.com/MuraliM1994)
📧 **Email:** [mm139300@gmail.com](mailto:mm139300@gmail.com)
📱 **Mobile:** +91 9059759840
📍 **Location:** Hyderabad, Telangana, India
