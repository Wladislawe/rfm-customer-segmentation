# RFM Customer Segmentation for E-Commerce

## Project Abstract
Performed **RFM (Recency, Frequency, Monetary) Analysis** on 541909 transactions from a UK online retail store to identify high-value customer segments and optimize marketing expences.

---

## Business Objective

**Goal:** Segment customers to prioritize marketing resources and maximize ROI.
**Problem:** Limited marketing budget ($500K/year) spread evenly across 4372 customers → inefficient.
**Solution:** RFM segmentation to target high-value customers and reactivate at-risk buyers.

---

## Dataset
- **Source:** [UCI Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)
- **Period:** December 2010 - December 2011
- **Size:** 541909 transactions | 4372 customers | 4070 products
- **Geography:** UK-based online gift retailer

---

## Methods

1. **Data Cleaning:**
   - Removed 135K transactions with missing CustomerID
   - Filtered out returns (negative Quantity)
   - Created `TotalPrice = Quantity × UnitPrice`

2. **RFM Calculation:**
   - **Recency (R):** Days since last purchase (snapshot date: Dec 10, 2011)
   - **Frequency (F):** Number of unique orders per customer
   - **Monetary (M):** Total lifetime spend

3. **Scoring:** Assigned quintile-based scores (1-5) for each metric

4. **Segmentation:** Grouped customers into 10 business segments based on RFM patterns

5. **Visualization:** Heatmaps, scatter plots, bar charts

---

## Key Findings
### 1. Champions drive 33% of revenue (10% of customers)
![Segment Distribution](results/segment_distribution.png)

- **Profile:** Recent buyers (avg 11 days), frequent orders (11×), high spend ($6,079)
- **Revenue:** $2.7M (33% of total)
- **Action:** VIP retention program

### 2. At Risk segment: $795K revenue at risk
- **Profile:** Inactive for 150+ days, but historically valuable ($1,283 avg spend)
- **Opportunity:** Win-back campaign (email + 20% discount)
- **Expected recovery:** 30-40% reactivation → +$240-320K revenue

### 3. Lost customers: not worth targeting
- **Profile:** One-time buyers, 230+ days inactive, low spend ($229)
- **Action:** Exclude from campaigns → save $50K/year

---

## Visualizations
### RFM Metrics by Segment
![Recency](results/rfm_recency_heatmap.png)
*Champions and Potential Loyalists have the lowest recency (most recent buyers)*

![Frequency](results/rfm_frequency_heatmap.png)
*Champions and Loyal Customers have 5-11× higher purchase frequency*

![Monetary](results/rfm_monetary_heatmap.png)
*Champions spend 6× more than average customer*

### Scatter Plot Analysis
![RFM Scatter](results/rfm_scatter.png)
*Top-right corner: Champions (frequent + recent). Bottom-right: Lost customers (infrequent + old)*

---

## Marketing Recommendations
| Segment | % Customers | % Revenue | Strategy | ROI Potential |
|---------|-------------|-----------|----------|---------------|
| Champions | 10.3% | 32.9% | VIP loyalty program | +$400K |
| Loyal Customers | 19.4% | 28.2% | Upsell premium products | +$230K |
| At Risk | 14.2% | 9.6% | Win-back campaign (20% off) | +$280K |
| Potential Loyalists | 13.3% | 7.1% | 2nd purchase incentive | +$150K |
| New Customers | 6.4% | 2.8% | Onboarding email series | +$80K |
| Lost | 8.0% | 3.4% | Exclude from campaigns | -$50K waste |

**Total potential uplift:** **+$1.1M revenue** (13% increase)

---

## Tools & Libraries
- **Language:** R (4.3+)
- **Libraries:** `tidyverse`, `ggplot2`, `lubridate`, `scales`
- **Techniques:** RFM analysis, quintile scoring, business segmentation, data visualization

---

## Repository Structure

- `rfm-customer-segmentation`
   - `data`
      - `Sales_Data.xlsx` raw dataset
   - `results`
      - `segment_summary.csv` aggregated segment data
      - visualisation graphs
   - `RFM analysis script.Rmd` R coding file
   - `RFM_analysis_script.html` html output of coding file
   - `README.md`
   - `README_RUS.md`

---

## How to Reproduce
### 1. Clone repository
git clone https://github.com/Wladislawe/rfm-customer-segmentation

### 2. Install dependencies
install.packages(c("tidyverse", "readxl", "lubridate", "scales", "ggplot2"))

---

## Business Impact Summary
**Before RFM**:

Marketing spend: $500K evenly across all 4,372 customers

**After RFM**:

Reallocate budget: 60% to Champions/Loyal (50% of customers, 61% revenue)

Win-back campaign: Recover $280K from At Risk

Cost savings: Exclude Lost → save $50K/year

Projected ROI: +13% revenue (+$1.1M)

---

## 📧 Contact
#### Vladislav Ovcharenko
##### quantitative BI and survey analyst

[LinkedIn Profile](https://www.linkedin.com/in/vlad-ovcharenko-9aa5013aa/?locale=en-US)
Email: vladgrinov890@gmail.com
Telegram: @vlad1s_love
