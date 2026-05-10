# NorthStar Urban Mobility and Logistics – Integrated Analytics and Database Investigation

**Author:** Mohammed Amaan Danish  
**Course:** Databases and Analytics (DBA)  
**Submission Date:** 05/05/2026  

## 1. Project Overview

NorthStar Urban Mobility and Logistics is a rapidly growing transport and delivery company operating across several UK cities. Despite increasing demand, the company has experienced deteriorating operational performance – higher delays, rising complaints, and increasing costs.

This project investigates **why** performance is deteriorating and **how** NorthStar’s fragmented data environment contributes to the problem. The analysis integrates:

- **SQL within R** for structured querying and aggregation
- **Python (Pandas, NumPy, Matplotlib, Seaborn)** for data cleaning, feature engineering, and visualisation
- **MongoDB Atlas** for NoSQL document storage and query optimisation

The final output is a **master dataset** (`orders_full_final.csv`) and an investigative report that identifies root causes and makes actionable recommendations.

---
## 2. Repository Structure
DBA_ASSIGNMENT/
├── README.md
├── requirements.txt
├── MohammedAmaanDanish_3214730_DBA.pdf
├── Google_Colab_Notebook/
│   └── DBA_Northstar.ipynb
├── data/
│   ├── customers.csv
│   ├── orders.csv
│   ├── deliveries.csv
│   ├── drivers.csv
│   ├── vehicles.csv
│   ├── hubs.csv
│   ├── incidents.csv
│   ├── complaints.csv
│   └── app_events.csv
└── Merged_dataset/
    └── orders_full_final.csv
---

## 3. Setup and Installation

### 4.1 Clone the Repository

```bash
git clone https://github.com/Amaan449/DBA_ASSIGNMENT.git
cd DBA_ASSIGNMENT

bash
pip install -r requirements.txt
Contents of requirements.txt:

text
pandas==2.0.3
numpy==1.24.3
matplotlib==3.7.2
seaborn==0.12.2
pymongo==4.5.0
dnspython==2.4.2
rpy2==3.5.11
Note: rpy2 requires R to be installed on your system (see section 4.3).

4.3 R Environment
The R code is executed within the Colab notebook using the rpy2 extension. However, if you want to run R code separately, install the following R packages:

r
install.packages(c("sqldf", "dplyr", "ggplot2", "corrplot", 
                   "scales", "lubridate", "tidyr", "RColorBrewer"))
4.4 MongoDB Atlas Setup
The project connects to a MongoDB Atlas cluster. You need:

A MongoDB Atlas account (free tier is sufficient).

A cluster (e.g., DBA).

A database named northstar_db.

A collection named customer_cases.

Update the MongoDB URI in the notebook (Cell where MongoClient is called) with your own credentials:

python
MONGO_URI = "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/?retryWrites=true&w=majority"
Security: Never commit your actual password to GitHub. Use environment variables or replace it before uploading. The repository’s .gitignore should exclude any file containing secrets.

5. Running the Analysis
5.1 Google Colab (Recommended)
The entire analysis is contained in Googlr_Colab_notebook/DBA_Northstar.ipynb. To run it:

Open Google Colab.

Click File → Upload notebook and select DBA_Northstar.ipynb.

In Colab, mount your Google Drive (optional) or upload the data/ folder manually.

Run all cells sequentially (Runtime → Run all).

The notebook will:

Clone the repository (if not already done)

Load and clean the nine datasets

Perform merges to create orders_full_final.csv

Run SQL‑in‑R queries and visualisations

Execute Python feature engineering and NumPy/Pandas analysis

Connect to MongoDB Atlas, insert documents, run CRUD operations, create indexes, and generate analytical insights.

5.2 Running Locally (Jupyter Notebook)
If you prefer to run locally:

Install R and R packages as described above.

Install Python packages using pip install -r requirements.txt.

Ensure the data/ folder is in the same directory as the notebook.

Launch Jupyter: jupyter notebook notebooks/final_analysis.ipynb

Note: The R cells (marked with %%R) require the rpy2 kernel. If you encounter issues, you can copy the R code into a separate .R file and run it in RStudio or R console.

6. Key Findings (from the report)
Finding	Evidence
Central zone is the worst performer	Average delay 3.0 hours, failure rate 34.5% (t‑test p < 0.001 vs. South)
Business and Medical services have highest delay rates	32.1% and 27.3% respectively, but complaint rates are uniform (silent churn risk)
Route overrides are concentrated in Airport outbound corridors	Airport → Central: 2.21 overrides, 3.54 hours delay, £17.51 fuel cost
EV fleet outperforms all other vehicle types	Lowest delay (1.28h), highest battery health (82.0%), highest volume (339 orders)
Relational database alone is insufficient for operational event data	MongoDB document model allows flexible, self‑describing records for app events and complaint histories
Indexing improves query performance	COLLSCAN → IXSCAN; estimated time from ~400ms to <5ms at 100k documents
7. Recommendations (from the report)
Recommendation	Priority
1. Central zone route infrastructure review	High
2. Business & Medical client service recovery programme	High
3. Mandatory proof‑of‑completion app enforcement	High
4. Proactive EV fleet maintenance scheduling	Medium
5. Contract driver zone onboarding reform	Medium
6. Deploy hybrid (relational + MongoDB) architecture	High
7. Extend to predictive analytics	Low
8. Troubleshooting
8.1 R cells not running in Colab
Ensure you have executed the cell that installs r-base and rpy2.

If you see Error: .onLoad failed, restart the Colab runtime and run the installation cells again.

8.2 MongoDB connection fails
Verify your Atlas cluster is active and IP whitelist includes 0.0.0.0/0 (for testing) or your Colab’s outgoing IP.

Double‑check the URI string – no extra spaces.

8.3 Missing orders_full_final.csv in outputs
The notebook automatically generates this file. If it does not appear, check that all merge cells ran without errors.

8.4 Low memory or slow execution in Colab
Colab’s free tier has ~12 GB RAM, which is sufficient for this dataset (1,250 rows). If you experience slowness, reduce the sample size in visualisation cells (e.g., sample(600)).

9. Dependencies and Versions
This project was developed and tested with:

Python: 3.10

R: 4.2+

MongoDB Atlas: M0 free tier (Shared Cluster)

Google Colab: Default runtime (2026)

For a complete list of Python packages with versions, see requirements.txt.

10. License and Acknowledgements
This project was completed as part of the Databases and Analytics (DBA) module at University Of WestLondon RAK.

All datasets are synthetic and provided for educational purposes only.

