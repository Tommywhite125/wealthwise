# Wealthwise — Family Financial Hub

A personal financial management tool for Australian families with multiple properties and investments. Runs entirely in the browser — no server, no account, no data leaves your device.

---

## Quick Start

1. Open `index.html` in any modern browser (Chrome, Safari, Firefox, Edge)
2. Click **⚙ Settings** (top right) and enter:
   - Your household name
   - Monthly take-home income
   - Income bracket (for peer benchmarking)
   - Anthropic API key (only needed for Screenshot Import and AI Suggestions)
3. Go to **Accounts** → add your bank accounts, loans, and credit cards
4. Import transactions via **↑ Import CSV** on any account card
5. The **Weekly Review** tab updates automatically with your data

---

## Features

| Tab | What it does |
|-----|-------------|
| 📊 Weekly Review | KPI strip, alerts, goal pace, budget RAG summary, 12-month cash flow waterfall |
| 💰 Family Budget | Budget table by category, transaction list, peer benchmarking, annual forecast |
| 🏦 Accounts | Account management, reconciliation ledger, CSV import |
| 🏠 Loans | Loan cards, amortisation table, rate sensitivity slider, weekly repayment schedule |
| 🏘 Properties | Property portfolio, equity tracking, rental yield, valuation history |
| 🎯 Goals | Annual and multi-year goal tracking with RAG pace indicators |
| 🧾 Income & Tax | Household income split, tax brackets, investment property tax analysis |
| 📷 Screenshot Import | Claude AI vision import for bank screenshots (3 modes) |

---

## CSV Import

Drop any bank CSV onto an account card. Supported formats:

- `Date, Description, Amount` (signed amount)
- `Date, Description, Debit, Credit, Balance` — ANZ / CBA style
- `Date, Description, Debit, Credit` — NAB style
- `Date, Amount, Description`

Date formats: `DD/MM/YYYY`, `YYYY-MM-DD`, `DD-MMM-YYYY`

A sample file is at `sample-data/sample.csv` — use it to test the import on a transaction account.

---

## Screenshot Import (Claude API)

Requires an Anthropic API key (~$0.003–0.008 per screenshot).

**Three modes:**
- **Accounts & Balances** — extracts all account names, types and balances from a bank app screenshot
- **Loan / Mortgage** — extracts full loan details (balance, rate, repayment, term)
- **Bulk Balance Update** — matches balances from a multi-account summary screenshot to your existing accounts

Paste a screenshot with **Cmd+V** / **Ctrl+V**, or drag and drop, or click to browse.

---

## Data & Backup

All data is stored in your browser's **localStorage**. Nothing is sent to any server except Anthropic (for AI features).

To back up or transfer your data: **⚙ Settings → Data & Backup → Export Backup (JSON)**

To restore: **⚙ Settings → Data & Backup → Import Backup (JSON)**

---

## AI Suggestions

Click **🤖 Get AI Suggestions** on the Weekly Review tab. Wealthwise sends your anonymised budget actuals, goal status, and loan data to Claude for analysis. Returns up to 5 ranked suggestions with estimated annual savings.

---

## Financial Year

Defaults to Australian FY (starts July 1). Change in **⚙ Settings → Financial Year** if you need a different start month.

---

## Technology

- Single HTML file — HTML + CSS + Vanilla JS, no frameworks
- localStorage persistence — works offline after first load
- Claude API (`claude-sonnet-4-20250514`) for vision and AI features
- Google Fonts: Playfair Display, DM Mono, DM Sans
