# Spotify User Behavior Analysis & Dashboard

## 📌 Project Overview
This project provides a comprehensive analysis of user engagement, subscription trends, and feature preferences for a music streaming platform. Using a dataset of 50,000 synthetic user records, I developed an interactive Power BI dashboard to help stakeholders identify churn risks and optimization opportunities.

## 🎯 Key Business Questions
- What are the primary drivers of user churn (inactivity)?
- How do listening habits vary across different demographic segments?
- Is the current advertisement model effectively converting "Free" users to "Premium"?
- Which features are most requested by the current user base?

## 📂 Project Structure
- `data/`: Contains the raw CSV dataset.
- `notebooks/`: Jupyter Notebooks with the Python ETL process.
- `pbix/`: Power BI project files.
- `assets/`: Documentation, icons, and images.
- `README.md`: Project documentation.

## 🛠️ Tool Stack
- **Data Processing:** Python (Pandas) inside Jupyter Notebooks
- **Environment Management:** Conda
- **Data Visualization:** Power BI Desktop
- **Calculations:** DAX (Data Analysis Expressions)
- **Documentation:** Markdown / GitHub

## ⚙️ ETL Process (Python)
Before importing to Power BI, the data underwent a cleaning process using Python to ensure quality:
- **Date Standardization:** Converted strings to `datetime` objects.
- **Boolean Mapping:** Transformed "Yes/No" columns into `1/0` for mathematical efficiency.
- **Feature Engineering:** Calculated user **Tenure** (months/years) based on a reference data (2025-12-31).
- **Data Quality:** Verified and handled outliers in listening habits.

## 📐 Data Modeling (Star Schema)
To optimize performance and filtering, the flat dataset was restructured into a **Star Schema**:
- **Fact Table:** `spotify_cleaned` containing metrics like listening hours, skips, and user status.
- **Dimension Tables:** Created specific dimensions for `Country`, `Subscription`, `Genre`, and `Primary Device`.
- **Relationships:** Established 1:N (one-to-many) relationships using Surrogate Keys (Index) to ensure data integrity and faster report rendering.

---
## 🚀 How to View the Project
1. Clone the repository.
2. Open the `.pbix` file in **Power BI Desktop**.
3. *[Optional]* Link to Power BI Service (if published).

---
## ⚙️ Environment Setup
To replicate this project's environment, use Conda:
```bash
conda create --name spotify-env python=3.12 pandas ipykernel
conda activate spotify-env
