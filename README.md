# Banking Portfolio Dashboard (Power BI)

A five-page Power BI report analysing the loan and deposit portfolio of **3,000 bank clients**. It breaks the bank's lending and deposits down by income band, nationality, banking relationship, investment advisor and how long each client has been with the bank.

<!-- To add a screenshot: export a page from Power BI Desktop as dashboard.png, upload it to this repo, and add the line ![Dashboard](dashboard.png) here. -->

---

## Key findings

| Finding | Number |
|---|---|
| Clients analysed | **3,000** (joined between 1995 and 2021) |
| Total lending (bank loans + business lending + credit cards) | **4.38 B** |
| Total deposits (deposits + savings + checking + foreign currency) | **3.77 B** |
| Overall loans-to-deposits ratio | **1.16**: lending exceeds the deposit base |
| Business lending share of total lending | **59%** (2.60 B), versus 1.77 B in bank loans |
| High-income clients (≥ 300K) | **15.2% of clients** but **21.6% of bank loans** |
| Largest borrower group by nationality | **European clients, 43.8%** of bank loans |
| Loyalty mix | Jade 44.4% · Silver 25.6% · Gold 19.5% · Platinum 10.6% |

**What this means for the business**
- **Funding gap.** Lending runs 16% ahead of deposits, mostly because of business lending, so the bank depends on funding beyond its client deposits.
- **Lending doesn't vary with risk.** The bank-loan-to-deposit ratio is almost the same at every risk weighting (0.86–0.89), which suggests higher-risk clients aren't being lent less.
- **Concentration risk.** European clients hold 43.8% of bank loans, and high-income clients borrow more than their share (21.6% of loans from 15.2% of clients). A downturn affecting either group would hit the loan book hardest.

*Figures computed directly from `Banking.csv`; income bands for this analysis are Low < 100K, Mid 100K–300K, High ≥ 300K. Currency is not specified in the source data.*

## Report pages

| Page | What it shows |
|---|---|
| **Home** | KPI cards for total clients, total loans, total deposits, credit card balance, fees and savings, with navigation buttons |
| **Loan Analysis** | Bank loans, business lending and credit cards by income band (donut), engagement length (bar), nationality (treemap) and banking relationship (combo chart) |
| **Deposit Analysis** | Deposits, savings, checking and foreign-currency accounts by income band, nationality and engagement length |
| **Summary** | Every headline KPI on one page, including average engagement length |
| **Drill Through** | Client-level table (advisor, engagement length, fees, credit cards), plus fees by loyalty tier and nationality |

Every page has slicers for **gender, banking relationship, investment advisor and joining period**.

## How I built it

- **Data model:** a star schema with the client fact table linked to lookup tables for **Banking Relationship**, **Investment Advisor**, **Gender** and **Period**
- **Calculated columns:** income band and engagement timeframe (how long each client has banked with the bank)
- **DAX measures** in a dedicated measures table: Total Clients, Total Loan, Bank Loan, Business Lending, Credit Cards, Total Deposit, Bank Deposit, Savings Account, Checking Accounts, Foreign Currency Account, Total Fees and Engagement Length
- **Navigation:** button-driven page navigation and a drill-through page from summary visuals down to individual clients

## Run it

1. Download `Banking Dashboard.pbix` and `Banking.csv`.
2. Open the `.pbix` in **Power BI Desktop**.
3. If prompted, point the data source at your copy of `Banking.csv`.

## Tech stack

Power BI Desktop · Power Query · DAX · star-schema data modelling · drill-through and navigation design
