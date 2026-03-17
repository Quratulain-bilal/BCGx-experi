# BCG Financial Chatbot — GFC Project (Task 5)

[![Tests](https://img.shields.io/badge/tests-15%20passed-brightgreen)]()
[![Python](https://img.shields.io/badge/python-3.8+-blue)]()
[![License](https://img.shields.io/badge/license-MIT-blue)]()

## 📋 Overview

A **rule-based AI financial chatbot** that provides instant responses to predefined financial queries using analyzed 10-K data from **Microsoft**, **Tesla**, and **Apple** (FY2022–FY2024).

This prototype demonstrates how simple if-else logic can be used to build a functional financial assistant capable of answering common questions about company performance metrics.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🏢 **Multi-Company Support** | Query data for Microsoft, Tesla, or Apple individually |
| 📊 **6 Financial Metrics** | Revenue, Net Income, Profit Margin, Assets, Cash Flow, Comparison |
| 💬 **Interactive CLI** | Real-time conversational interface |
| ✅ **Test Coverage** | 15 comprehensive tests (all passing) |
| 📈 **FY2022-FY2024 Data** | Three years of financial data from 10-K filings |

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- No external dependencies required (uses only built-in libraries)

### Installation
```bash
# Clone the repository
git clone https://github.com/Quratulain-bilal/BCGx-experi.git
cd Task Five

# No installation needed - runs with standard Python library
```

### Running the Chatbot
```bash
# Start interactive chatbot
python chatbot.py

# Run test suite
python test_chatbot.py
```

---

## 💬 Supported Queries

### 1. Total Revenue
```
You: What is the total revenue?
Chatbot: Total Revenue (FY2024):
  - Microsoft: $245.12B
  - Tesla: $97.69B
  - Apple: $391.04B

You: What is Microsoft's revenue?
Chatbot: Microsoft's total revenue for FY2024 is $245.12B.
```

### 2. Net Income Change
```
You: How has net income changed?
Chatbot: Net Income Change (FY2023 to FY2024):
  - Microsoft: increased by 21.8% ($72.36B -> $88.14B)
  - Tesla: decreased by 52.6% ($14.97B -> $7.09B)
  - Apple: decreased by 3.4% ($97.00B -> $93.74B)

You: How has Tesla's net income changed?
Chatbot: Tesla's net income decreased from $14.97B (FY2023) to $7.09B (FY2024), a change of -52.6%.
```

### 3. Profit Margin
```
You: What is the profit margin?
Chatbot: Profit Margins (FY2024):
  - Microsoft: 36.0%
  - Tesla: 7.3%
  - Apple: 24.0%

You: What is Apple's profit margin?
Chatbot: Apple's profit margin for FY2024 is 24.0% (Net Income $93.74B / Revenue $391.04B).
```

### 4. Total Assets
```
You: What are the total assets?
Chatbot: Total Assets (FY2024):
  - Microsoft: $512.16B
  - Tesla: $122.07B
  - Apple: $364.98B
```

### 5. Operating Cash Flow
```
You: What is the operating cash flow?
Chatbot: Operating Cash Flow (FY2024):
  - Microsoft: $118.55B
  - Tesla: $11.53B
  - Apple: $118.25B

You: What is Microsoft's cash flow?
Chatbot: Microsoft's operating cash flow for FY2024 is $118.55B (48.4% of revenue).
```

### 6. Company Comparison
```
You: Compare all companies
Chatbot: Company Comparison (FY2024):
Metric                 Microsoft        Tesla        Apple
------------------------------------------------------------
Revenue ($B)              245.12        97.69       391.04
Net Income ($B)            88.14         7.09        93.74
Total Assets ($B)         512.16       122.07       364.98
Total Liabilities ($B)    243.69        48.26       308.03
Operating CF ($B)         118.55        11.53       118.25
Profit Margin (%)           36.0         7.3        24.0
```

### 7. Help Menu
```
You: help
Chatbot: I can answer the following financial queries (FY2022-FY2024):

  1. "What is the total revenue?" (or add a company name)
  2. "How has net income changed?"
  3. "What is the profit margin?"
  4. "What are the total assets?"
  5. "What is the operating cash flow?"
  6. "Compare all companies"

Supported companies: Microsoft, Tesla, Apple
Tip: Add a company name to any query for company-specific data.
Example: "What is Microsoft's revenue?"
```

---

## 🏗️ Architecture

### How It Works

```
┌─────────────────┐     ┌──────────────────┐     ┌─────────────────┐
│   User Input    │ ──► │  Company Detect  │ ──► │  Query Matching │
│  (Natural Lang) │     │ (MSFT/TSLA/AAPL) │     │  (Rule-Based)   │
└─────────────────┘     └──────────────────┘     └─────────────────┘
                                                        │
                                                        ▼
┌─────────────────┐     ┌──────────────────┐     ┌─────────────────┐
│   Formatted     │ ◄── │   Data Lookup    │ ◄── │  Function Call  │
│   Response      │     │  (FY2022-2024)   │     │   Execution     │
└─────────────────┘     └──────────────────┘     └─────────────────┘
```

### Code Structure

```
chatbot.py
├── DATA                      # Financial data dictionary (3 companies × 5 years)
├── get_total_revenue()       # Query handler for revenue
├── get_net_income_change()   # Query handler for net income trends
├── get_profit_margin()       # Query handler for profit margins
├── get_total_assets()        # Query handler for total assets
├── get_cash_flow()           # Query handler for operating cash flow
├── compare_companies()       # Query handler for company comparison
├── detect_company()          # Company name detection from input
├── simple_chatbot()          # Main routing logic (if-else rules)
└── run_chatbot()             # Interactive CLI loop
```

---

## 📊 Financial Data Source

Data extracted from **10-K Annual Reports** (FY2022-FY2024):

| Company | FY2024 Revenue | FY2024 Net Income | FY2024 Profit Margin |
|---------|----------------|-------------------|---------------------|
| Microsoft | $245.12B | $88.14B | 36.0% |
| Tesla | $97.69B | $7.09B | 7.3% |
| Apple | $391.04B | $93.74B | 24.0% |

---

## ✅ Test Results

```
============================================================
  CHATBOT TEST RESULTS
============================================================

[PASS] Query: "What is the total revenue?"
[PASS] Query: "What is Microsoft's revenue?"
[PASS] Query: "What is Tesla's revenue?"
[PASS] Query: "What is Apple's revenue?"
[PASS] Query: "How has net income changed?"
[PASS] Query: "How has net income changed for Microsoft?"
[PASS] Query: "What is the profit margin?"
[PASS] Query: "What is Tesla's profit margin?"
[PASS] Query: "What are the total assets?"
[PASS] Query: "What is Apple's total assets?"
[PASS] Query: "What is the operating cash flow?"
[PASS] Query: "What is Microsoft's cash flow?"
[PASS] Query: "Compare all companies"
[PASS] Query: "help"
[PASS] Query: "random nonsense xyz"

============================================================
  Results: 15/15 tests passed
============================================================
```

---

## ⚠️ Limitations

| Limitation | Impact |
|------------|--------|
| **Rule-Based Logic** | Only responds to predefined query patterns (no NLP/ML) |
| **Limited Companies** | Supports only Microsoft, Tesla, and Apple |
| **Static Data** | FY2022-FY2024 only; not real-time |
| **No Context Memory** | Cannot handle multi-turn conversations |
| **Keyword Matching** | May miss variations of queries |
| **No Learning** | Cannot improve from interactions |

---

## 🔮 Future Enhancements

- [ ] Integrate NLP library (spaCy, NLTK) for better query understanding
- [ ] Add more companies and financial metrics
- [ ] Connect to live financial data APIs
- [ ] Implement conversation memory and context
- [ ] Add web/GUI interface
- [ ] Support follow-up questions
- [ ] Add data visualization (charts, graphs)

---

## 📁 Project Structure

```
Task Five/
├── chatbot.py           # Main chatbot implementation
├── test_chatbot.py      # Test suite (15 tests)
├── README.md            # Documentation
└── Financial_Chatbot.zip # Archive of project files
```

---

## 👤 Author

**BCG x GFC Project — Task 5**

A rule-based prototype demonstrating fundamental chatbot architecture for financial data queries.

---

## 📄 License

MIT License — Educational/Portfolio Project
