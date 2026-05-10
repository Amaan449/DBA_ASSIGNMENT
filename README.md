# DBA Assignment: NorthStar Urban Mobility Investigation

## Project Overview
This repository contains the complete code and data for the NorthStar Urban Mobility and Logistics investigation report. The project uses Python, R, SQL, and MongoDB to identify root causes of operational failures.

👤 **Author:** Amaan449  
📅 **Date:**  05/05/2026  
🎓 **Course:** Databases and Analytics (DBA)  

**Final Report:** [MohammedAmaanDanish_32147390_DBA_Report.pdf](MohammedAmaanDanish_32147390_DBA_Report.pdf)

## Repository Structure
DBA_ASSIGNMENT/
├── README.md
├── requirements.txt
├── NorthStar_Report.pdf
├── notebooks/
│   └── final_analysis.ipynb
├── data/
│   └── All original.csv  
│   ├── orders_full_final.csv
Getting Started
1. Clone the Repository
bash
git clone https://github.com/Amaan449/DBA_ASSIGNMENT.git
cd DBA_ASSIGNMENT
2. Set Up Environment
Python: Install required packages:

bash
pip install -r requirements.txt
R: Install the following packages: sqldf, dplyr, ggplot2, corrplot, scales, lubridate, tidyr, RColorBrewer.

3. Run the Notebook
Open notebooks/final_analysis.ipynb in Google Colab or Jupyter and run all cells.

Key Findings
Central zone has the worst performance averaging 3.0 hours delay with a 34.5% failure rate.

Business and Medical services have the highest delay rates (32.1% and 27.3%).

Manual route overrides are linked to higher delays and costs, pointing to planning algorithm failures.

SQL in R and MongoDB Atlas queries confirmed that operational failures are not evenly distributed across hubs, zones, or vehicle types.

Tools & Technologies
Python (Pandas, NumPy, Matplotlib, Seaborn)

R (sqldf, ggplot2)

MongoDB Atlas

Google Colab / Jupyter Notebooks
