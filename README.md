# 📦 Supply Chain Analytics Automation

<div align="center">

**End-to-end automated supply chain analytics solution**

[View Dashboard](https://lookerstudio.google.com/s/ldCOeafvUYI) • [Report Issues](../../issues) • [Request Features](../../issues)

---

</div>

## 🌟 Introduction

This project implements an **end-to-end supply chain analytics solution** that automates data extraction, transformation, and visualization. By leveraging modern automation and analytics tools, we've created a seamless pipeline that processes supply chain data from Gmail triggers through to interactive dashboards.

The system **automatically extracts data** from CSV files received via email, performs **comprehensive statistical analysis**, and presents insights through **interactive dashboards**. This enables real-time monitoring of supply chain KPIs, revenue metrics, and operational efficiency indicators.

### ✨ Key Highlights

- 🚀 **Fully Automated**: From email trigger to dashboard updates
- 📊 **Real-time Analytics**: Live KPI monitoring and tracking
- 💹 **Multi-currency Support**: Automatic USD to INR conversion
- 📈 **Executive Ready**: Professional dashboards for decision-making
- 🔄 **Scalable Pipeline**: Handles growing data volumes effortlessly

---

## 🏗️ Architecture Overview

<div align="center">

```mermaid
graph LR
    A[📧 Gmail Trigger] -->|CSV Files| B[⚙️ n8n Automation]
    B -->|Transform| C[(🗄️ Supabase DB)]
    C -->|Connect| D[📊 Quadratic Analytics]
    D -->|Process| E[📈 Looker Studio]
    
    style A fill:#EA4335,stroke:#fff,stroke-width:2px,color:#fff
    style B fill:#9E3FFF,stroke:#fff,stroke-width:2px,color:#fff
    style C fill:#3ECF8E,stroke:#fff,stroke-width:2px,color:#fff
    style D fill:#7C3AED,stroke:#fff,stroke-width:2px,color:#fff
    style E fill:#4285F4,stroke:#fff,stroke-width:2px,color:#fff
```

**📸 Detailed Workflow:** Refer to `n8n_workflow.jpeg` in the repository

</div>

### 📋 Pipeline Flow

```
📧 Gmail → ⚙️ n8n Workflow → 🗄️ Supabase PostgreSQL → 📊 Quadratic → 📈 Looker Studio
```

---

## 🛠️ Tools & Technologies

<table>
<tr>
<td width="25%" align="center">

### <img src="https://n8n.io/favicon.ico" width="20"/> n8n

**Workflow Automation**

</td>
<td width="25%" align="center">

### <img src="https://supabase.com/favicon/favicon-32x32.png" width="20"/> Supabase

**Cloud Database**

</td>
<td width="25%" align="center">

### 📊 Quadratic

**Analytics Platform**

</td>
<td width="25%" align="center">

### 📈 Looker

**Data Visualization**

</td>
</tr>
</table>

### 1️⃣ **n8n** - Workflow Automation Engine

<details>
<summary>Click to expand details</summary>

**Purpose:** Orchestrates the entire data pipeline

**Key Functions:**
- ✉️ Gmail trigger for incoming emails with CSV attachments
- 📄 CSV data extraction and parsing
- 🔄 Data transformation and aggregation
- 💾 Database insertion automation
- ⚡ Error handling and retry mechanisms

**Workflow Components:**
- **Trigger Node**: Monitors Gmail for supply chain data
- **Extract Nodes**: Processes Aggregate & Order_Line data
- **Transform Nodes**: Cleans and structures data
- **Database Nodes**: Inserts into Supabase tables

</details>

### 2️⃣ **Supabase (PostgreSQL)** - Cloud Database

<details>
<summary>Click to expand details</summary>

**Purpose:** Centralized data storage and management

**Key Functions:**
- 💾 Real-time data storage
- 🔐 Secure online database connection
- 📚 Data versioning and history
- 🔌 API endpoints for data access
- 🔄 Automatic backups

**Database Schema:**
- `aggregate_data` - Summary level metrics
- `order_line_data` - Detailed transaction records
- `kpi_calculations` - Computed performance indicators

</details>

### 3️⃣ **Quadratic** - Advanced Analytics Platform

<details>
<summary>Click to expand details</summary>

**Purpose:** Statistical analysis and data preprocessing

**Key Functions:**
- 🧹 Data preprocessing and cleaning
- 💱 Currency conversion (USD to INR)
- 📅 Date format standardization
- 💰 Revenue calculations
- 📊 KPI computations
- 📈 Statistical analysis

**Analysis Performed:**
- Descriptive statistics
- Trend analysis
- Correlation studies
- Performance benchmarking
- Predictive modeling

</details>

### 4️⃣ **Looker Studio** - Data Visualization

<details>
<summary>Click to expand details</summary>

**Purpose:** Interactive dashboard and reporting

**Key Functions:**
- 📊 Real-time data visualization
- 🎯 KPI monitoring
- 📈 Trend analysis
- 📑 Executive reporting
- 📱 Mobile-responsive design

**Dashboard Features:**
- Executive summary
- Operational metrics
- Financial analysis
- Geographic distribution
- Time-series trends

</details>

---

## 📊 Data Source & Dashboard

<div align="center">

### 📚 **Data Source**
[Codebasics Supply Chain Dataset](https://codebasics.io/)

### 🎨 **Live Dashboard**
[![View Dashboard](https://img.shields.io/badge/View%20Live%20Dashboard-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://lookerstudio.google.com/s/ldCOeafvUYI)

*Alternatively, refer to `supply_chain_pdf` for static dashboard views*

### 📄 **Detailed Analysis**
> For comprehensive insights, primary & secondary analysis, and data-driven decisions, please refer to:
> 
> 📖 **`Analytics_Report.pdf`**

</div>

---

## 🔄 Data Processing Pipeline

### 📥 **Stage 1: Data Extraction** (n8n)

```
📧 Email Received → 📎 CSV Attached → 🔍 Extract Data → ✅ Validate Format
```

- Automated email monitoring for CSV files
- Parallel processing of multiple data sources:
  - **Aggregate Data**: 128 items (summary metrics)
  - **Order Line Data**: 226 items (detailed transactions)
- Data validation and error handling
- Automatic retry mechanisms
- **Output**: 354 total items processed

---

### 💾 **Stage 2: Data Storage** (Supabase)

```
🔄 Receive Data → 🗂️ Structure Tables → 💾 Insert Records → 🔗 Create Relations
```

- Structured data insertion into PostgreSQL tables
- Relationship mapping between aggregate and order data
- Timestamp tracking for data lineage
- Backup and recovery capabilities
- Real-time API access

---

### 🧮 **Stage 3: Data Preprocessing** (Quadratic)

<table>
<tr>
<td width="50%">

#### 💱 Currency Conversion
- **USD to INR** conversion
- Real-time exchange rates
- Historical rate tracking
- Accurate period comparisons

#### 📅 Date Standardization
- Unified date format
- Timezone normalization
- Period grouping (daily/weekly/monthly)
- Fiscal year alignment

</td>
<td width="50%">

#### 💰 Revenue Calculations
- Total revenue aggregation
- Revenue by product category
- Revenue by region
- Profit margin calculations
- YoY growth metrics

#### 📊 KPI Computations
- Average delivery delay
- On-time delivery %
- Order fulfillment rate
- Inventory turnover
- Customer satisfaction

</td>
</tr>
</table>

---

### 📈 **Stage 4: Visualization** (Looker Studio)

```
📊 Connect Data → 🎨 Design Dashboard → 📱 Deploy Live → 🔄 Auto-refresh
```

- Executive dashboard with key metrics
- Interactive trend analysis charts
- Geographic distribution maps
- Drill-down capabilities
- Automated report generation
- Mobile-responsive design

---

## 📊 Key Performance Indicators (KPIs)

<div align="center">

| 📈 Metric | 📝 Description |
|-----------|----------------|
| **⏰ On Time** | Percentage of orders delivered by the scheduled delivery date |
| **📦 In Full** | Percentage of orders delivered with the complete ordered quantity |
| **✅ On Time In Full (OTIF)** | Combined metric measuring orders delivered both on time and in full |
| **📊 In Line Rate** | Percentage of order lines fulfilled according to specifications |
| **📈 Volume Rate** | Ratio of actual delivered volume to requested order volume |
| **🛒 Total Orders** | Total count of customer orders placed in the system |
| **📋 Total Order Lines** | Total count of individual line items across all orders |
| **⏱️ Average Delay** | Mean time delay between scheduled and actual delivery dates |
| **💸 Revenue Loss** | Potential revenue lost due to unfulfilled or delayed orders |

</div>

---

## 🚀 Getting Started

### 📋 Prerequisites

```bash
✅ n8n instance (self-hosted or cloud)
✅ Supabase account with PostgreSQL database
✅ Quadratic account
✅ Looker Studio access
✅ Gmail account for email triggers
```

## 📁 Project Structure

```
supply-chain-analytics/
│
├── 📂 n8n/
│   ├── workflows/
│   │   ├── supply_chain_automation.json
│   │   └── n8n_workflow.jpeg
│   └── credentials/
│       └── .env.example
│
├── 📂 database/
│   ├── schema.sql
│   ├── migrations/
│   │   ├── 001_initial_schema.sql
│   │   └── 002_add_indexes.sql
│   └── sample_data/
│       └── test_data.csv
│
├── 📂 quadratic/
│   ├── notebooks/
│   │   ├── preprocessing.ipynb
│   │   ├── kpi_calculations.ipynb
│   │   ├── statistical_analysis.ipynb
│   │   └── currency_conversion.ipynb
│   └── scripts/
│       └── automation.py
│
├── 📂 looker/
│   ├── dashboards/
│   ├── reports/
│   │   └── supply_chain_pdf
│   └── screenshots/
│
│
├── 📄 README.md
└── 📄 CONTRIBUTING.md
```


## 🤝 Contributing

We welcome contributions! 
For major changes, please open an issue first to discuss what you would like to change.

---

**Project Link:** [https://github.com/yourusername/supply-chain-analytics](https://github.com/Rajputmansi7/supply-chain-analytics)

</div>

---

## 🙏 Acknowledgments

<div align="center">

Special thanks to:

🙌 **[Codebasics](https://codebasics.io/)** - For providing the supply chain dataset

⚙️ **[n8n Community](https://n8n.io/)** - Workflow automation support

🗄️ **[Supabase Team](https://supabase.com/)** - Excellent database platform

📊 **[Quadratic](https://quadratic.io/)** - Powerful analytics capabilities

📈 **[Looker Studio](https://lookerstudio.google.com/)** - Intuitive visualization tools

</div>

---

<div align="center">

### ⭐ If you find this project useful, please give it a star!

![Star History](https://img.shields.io/github/stars/Rajputmansi7/Supply-Chain-Analytics-using-n8n?style=social)

**Made with ❤️ for the Supply Chain Analytics Community**

</div>
