# 🤖 AgentFinancialAnalyst

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-Framework-orange)](https://www.langchain.com/)
[![yFinance](https://img.shields.io/badge/Data-yFinance-green)](https://pypi.org/project/yfinance/)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](LICENSE)

An **AI Agent to perform as a Financial Analyst** 📈  
This project explores how to combine **LangChain** with a reasoning engine (**LLM – GPT-4**) to orchestrate an agent capable of scanning market information, analyzing technical indicators, and producing **professional financial research reports**.

---

## ✨ Features

- ✅ Validate tickers and fetch historical price data with **yfinance**  
- ✅ Compute **technical indicators**: RSI(14), MACD (+ signal + histogram), SMA 10/20, returns 1D and 5D  
- ✅ Launch **contextualized news searches** based on indicators (momentum, overbought/oversold, etc.)  
- ✅ Extract **valuation snapshot**: current price, market cap, P/E, 52-week range, volume  
- ✅ Generate structured reports with:  
  - Executive Summary  
  - Current Valuation  
  - Recent Developments  
  - Analyst Perspective  

---

## ⚙️ Workflow

1. **Input**: stock ticker (e.g., `AAPL`)  
2. **Indicators**: compute RSI, MACD, SMA, short-term returns  
3. **News Search**: queries are dynamically adjusted depending on indicator values  
   - RSI ≥ 70 → *overbought / profit taking / valuation concerns*  
   - RSI ≤ 30 → *oversold / rebound catalyst / upgrades*  
   - MACD hist > 0 → *momentum / guidance raise*  
   - MACD hist < 0 → *guidance cut / headwinds*  
   - ret_5d ≥ 3% → why it went up last week  
   - ret_1d ≤ −2% → why it fell today  
4. **Report Generation**: LLM synthesizes findings into a professional report  

---

## 🛠️ Tech Stack

- [LangChain](https://www.langchain.com/) + **LangGraph** for orchestration  
- [OpenAI GPT-4](https://platform.openai.com/) as reasoning engine  
- [Tavily API](https://docs.tavily.com) for news search  
- [yFinance](https://pypi.org/project/yfinance/) for market data  
- [pandas](https://pandas.pydata.org/), [numpy](https://numpy.org/), [matplotlib](https://matplotlib.org/) for analysis & visualization  
- [tenacity](https://tenacity.readthedocs.io/) for retries  

---

## 🚀 Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/albertoalonsso/AgentFinancialAnalyst.git
cd AgentFinancialAnalyst
