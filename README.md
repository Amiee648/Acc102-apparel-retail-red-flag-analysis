# Acc102-apparel-retail-red-flag-analysis
 A Python-based financial red flag screening of North American apparel retailers.
# A Beginner-friendly Financial Red Flag Screener for Sportswear and Apparel Retail Companies
## Quick Access
- Main notebook:https://github.com/Amiee648/Acc102-apparel-retail-red-flag-analysis/blob/main/A%20Beginner-friendly%20Financial%20Red%20Flag%20Screener%20for%20Sportwear%20and%20Apparel%20Retails%20Companies.ipynb

## Problem
This project builds a simple financial red flag screener for selected sportswear and apparel retail companies. The purpose is to help beginner investors and business students identify potential warning signs by comparing revenue growth with inventory growth, fixed asset growth, and accounts receivable growth over the most recent fiscal years.

This notebook does not aim to prove fraud. Instead, it provides a simple and interpretable screening approach for identifying companies whose business expansion may not be fully supported by sales growth. The output is intended to help users compare firms, spot possible warning signals, and create a watchlist for further analysis.

## Target User
This tool is designed for beginner investors and business students. It provides a simple, automated screening framework to compare peer companies within the Apparel Retail industry and identify potential risks before making investment decisions.

## Data Source
**Source:** WRDS (Compustat - Fundamentals Annual). 
*   **Sample:** Top North American apparel retailers (e.g., NKE, LULU, UAA, VFC, SKX, COLM, CROX, FL).
*   **Timeframe:** 2018 to present.
*   **Date Accessed:** April 18, 2026.
*   *Note on Data Accessibility:* WRDS is a restricted academic database requiring institutional access. The raw dataset is not uploaded to this repository due to compliance and file size constraints. Instead, the data is extracted dynamically via the `wrds` Python library. Users must have valid WRDS credentials to run the notebook.
*   **access instruction:** Users with institutional WRDS access can reproduce the data extraction step directly in the notebook.

## Methods
1. Load and clean the data from WRDS.
2. Calculate year-over-year growth rates for sales, inventory, fixed assets, and receivables.
3. Apply red flag rules to compare each metric against sales growth.
4. Generate a warning score for each company-year observation.
5. Aggregate warning scores to identify outliers.
6. Visualize both the overall risk ranking and the detailed growth divergence for top risk companies.

## Key Findings
- **Lululemon (LULU)**, **Crocs (CROX)**, and **Foot Locker (FL)** display the highest cumulative warning scores.
- **Columbia Sportswear (COLM)** and **Skechers (SKX)** appear more stable in this screening.
- The most common red flag drivers are:
  - inventory growth outpacing sales,
  - fixed asset growth outpacing sales,
  - receivables growth outpacing sales.

## How to Run
1. **Prerequisites:** Ensure you have a valid WRDS account with access to Compustat data. If not, contact your academic institution for access.
2. **Install Dependencies:** Install required packages using pip:
   ```bash
   pip install -r requirements.txt
   ```
   Or manually:
   ```bash
   pip install pandas wrds matplotlib
   ```
3. **Set Credentials:** Open the notebook and replace `"your_username"` in the WRDS connection line with your actual WRDS username.
4. **Run the Notebook:** Open the notebook in Jupyter Lab/Notebook and execute all cells sequentially. The analysis will take a few minutes to download and process the data.
5. **View Outputs:** The notebook will generate visualizations and display results directly in the output cells.

## Repository Structure
*   `A Beginner-friendly Financial Red Flag Screener for Sportswear and Apparel Retail Companies.ipynb`: The main Jupyter notebook containing the complete analysis workflow.
*   `requirements.txt`: List of Python dependencies required to run the notebook.
*   `figures/`: Directory containing output visualizations (e.g., `three_companies.png` for the multi-dimensional red flag charts).
*   `README.md`: Project documentation.

## Limitations
- This notebook is a screening tool, not a definitive judgment of quality or fraud.
- It identifies unusual financial patterns, but not the exact reason behind them.
- Further qualitative analysis is required using company filings, earnings commentary, and industry context.
- The sample is limited to eight U.S.-listed apparel retail companies and may not generalize to other sectors.
- The screening thresholds are currently set at 15% for inventory and fixed asset divergence, and 20% for receivables divergence.
- Growth rate calculations may be sensitive to one-off events, accounting changes, or seasonal fluctuations.
- The analysis assumes consistent financial reporting standards across companies, which may not always hold true.
