# Maharashtra Dairy Supply Chain Analysis

### A Python + Excel analysis of district-wise milk procurement and distribution across Maharashtra, built from real government open data (data.gov.in) — examining sector structure, geographic concentration, and self-sufficiency across 33 districts.

<a href='https://github.com/merupo/maharashtra-dairy-supply-chain-analysis/blob/main/maharashtra_dairy_supply_chain_analysis_files/Dashboard.png'>View the Dashboard</a>

# Business Question

How is Maharashtra's dairy procurement structured across Government, Co-operative, and Private sectors, how geographically concentrated is the supply chain, and which districts depend most heavily on external milk supply?

# Why This Project

My dad works at Heritage Foods, one of India's major private dairy players, which gave me a personal window into how large the dairy supply chain really is. That connection led me to this dataset — a real, government-published report on Maharashtra's district-wise milk procurement, sourced directly from the Maharashtra Dairy Development Department via data.gov.in.

# Dataset
- Source: <a href='https://ap.data.gov.in/resource/district-wise-milk-procurement-and-distribution-report-day-lakhs-state-maharashtra-july'>District-wise Milk Procurement and Distribution Report, Maharashtra Dairy Development Department (data.gov.in), July 2025</a>
- Coverage: 33 districts across 6 administrative divisions (Pune, Nashik, Aurangabad, Konkan, Amravati, Nagpur), July 2025
- Note: Raw government data required real cleaning, embedded regional subtotal rows, inconsistent district name abbreviations, and a corrupted column header were all addressed during processing <a href=''>(see notebook)</a>

# KPIs
| KPI | Definition | Purpose |
| :--- | :--- | :--- |
| **Sector Share (%)** | Co-operative vs. Private share of procurement, by division | Reveals who controls the supply chain regionally |
| **Division-Level Roll-up** | Total procurement & receipt, aggregated by division | Measures geographic concentration |
| **Self-Sufficiency Ratio** | Basic Procurement ÷ Total Procurement & Receipt | Flags import-dependent districts |
| **Channel Mix (%)** | Pouch / Retail / Bi-Products / Conversion as % of total sale | Shows how milk is monetized differently by region |

# Method
1. Data cleaning & validation (Python/pandas, Google Colab) — removed embedded subtotal rows, fixed a corrupted column name, standardized abbreviated district names, mapped all 33 districts to their 6 official divisions
2. KPI calculation (Python) — Self-Sufficiency Ratio and Procurement-to-Sale Ratio computed and validated against the government's own reported district total (exact match)
4. Dashboard (Excel) — PivotTables, PivotCharts, and verified percentage calculations

# Key Findings
- **Private sector dominates:** Government procurement is 0% across all 33 districts; the state splits 76.7% Private vs. 23.3% Co-operative — though this varies sharply by region (Konkan is Co-op-majority at 56.9%, Amravati is 97.8% Private)
- **Extreme geographic concentration:** Pune Division alone handles 56.6% of the state's total dairy supply (159.9 of 283.69 lakh litres/day)
- **Major cities are import-dependent, not self-sufficient:** Thane (0.5%), Raigad (0%), and Nagpur (28%) rely almost entirely on external supply rather than local procurement
- **Channel mix varies by region:** Nagpur and Konkan move milk primarily through direct pouch sale (80%+), while Aurangabad and Amravati lean on retail sale

Full findings and methodology: <a href='https://github.com/merupo/maharashtra-dairy-supply-chain-analysis/blob/main/maharashtra_dairy_supply_chain_analysis_files/Maharashtra_Dairy_Supply_Chain_Case_Study.docx'>Maharashtra_Dairy_Supply_Chain_Case_Study</a>

# Data Quality Note

Cleaned district-level totals (282.49 lakh litres) were validated against the government's own reported district total, confirming an exact match. The statewide Grand Total (283.69) additionally includes Mumbai and Mahanand federation-level volume not attributed to individual districts.

# Tools Used
- Python (pandas, Google Colab) — data cleaning, validation, KPI calculation
- Microsoft Excel — PivotTables, PivotCharts, dashboard
