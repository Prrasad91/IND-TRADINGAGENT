 #####**IND-TRADINGAGENT**
TradingAgents Framework  
TradingAgents is a multi-agent trading framework designed to replicate the dynamics of Indian financial markets. By deploying specialized LLM-powered agents—such as fundamental analysts, sentiment experts, technical analysts, traders, and risk management teams—the platform collaboratively evaluates market conditions and informs trading decisions tailored to the Indian market. Additionally, these agents engage in dynamic discussions to identify the most effective strategies for navigating India's unique trading environment.
  Analyst Team  
-Fundamentals Analyst: Evaluates financial statements of Indian companies, analyzing metrics like P/E ratio, ROE, and debt levels to identify intrinsic values and potential risks.  
- Sentiment Analyst: Tracks sentiment across Indian social media platforms, forums, and news outlets using sentiment scoring algorithms to gauge short-term market mood.  
-News Analyst: Monitors domestic and global news, including RBI announcements, government policies, and macroeconomic indicators, interpreting their impact on Indian market conditions.  
-Technical Analyst: Utilizes technical indicators such as Bollinger Bands, MACD, and RSI to identify trading patterns and forecast price movements in Indian stocks, indices, and commodities.  

 Researcher Team  
The Researcher Team consists of bullish and bearish researchers who critically evaluate insights from the Analyst Team. Through structured debates, they balance potential gains against risks, ensuring strategies are tailored to the Indian market's volatility and dynamics.  

 Trader Agent  
The Trader Agent synthesizes reports from analysts and researchers to make informed trading decisions. It determines the timing and magnitude of trades based on comprehensive insights into Indian market trends, liquidity, and sentiment.  

 Risk Management and Portfolio Manager  
-Risk Management Team: Continuously assesses portfolio risk by analyzing market volatility, liquidity, and sector-specific risks in the Indian market. It adjusts trading strategies and provides detailed risk assessment reports.  
-Portfolio Manager: Reviews transaction proposals and approves or rejects them based on risk evaluations. Approved orders are sent to the simulated exchange for execution, mimicking the operations of Indian stock exchanges like NSE and BSE.  


Install dependencies:  
bash
pip install -r requirements.txt  
  

 Required APIs  
-Financial Data: Use the FinnHub API for stock data.  
  bash
  export FINNHUB_API_KEY=$YOUR_FINNHUB_API_KEY  
    
-LLM Agents: Use the OpenAI API for agent operations.  
  bash
  export OPENAI_API_KEY=$YOUR_OPENAI_API_KEY  
    

 CLI Usage  
Run the CLI to interact with the framework:  
bash
python -m cli.main  
  
Select Indian tickers, dates, LLMs, and research depth. The interface will display results dynamically, allowing you to track the agents' progress.  

  

 TradingAgents Package  

 Implementation Details  
TradingAgents is built using LangGraph for modularity and flexibility. It leverageso1-preview andgpt-4o for deep and fast thinking LLMs. For cost-effective testing, useo4-mini andgpt-4.1-mini, as the framework makes frequent API calls.  

 Python Usage  
To use TradingAgents in your code:  
python
from tradingagents.graph.trading_graph import TradingAgentsGraph  
from tradingagents.default_config import DEFAULT_CONFIG  

ta = TradingAgentsGraph(debug=True, config=DEFAULT_CONFIG.copy())  

 Forward propagate  
_, decision = ta.propagate("RELIANCE", "2025-07-06")  
print(decision)  
  

Customize configurations for Indian markets:  
python
from tradingagents.graph.trading_graph import TradingAgentsGraph  
from tradingagents.default_config import DEFAULT_CONFIG  

 Custom configuration  
config = DEFAULT_CONFIG.copy()  
config["deep_think_llm"] = "gpt-4.1-nano"  
config["quick_think_llm"] = "gpt-4.1-nano"  
config["max_debate_rounds"] = 2  
config["online_tools"] = True  

ta = TradingAgentsGraph(debug=True, config=config)  

 Forward propagate  
_, decision = ta.propagate("TCS", "2025-07-06")  
print(decision)  
  

 Contributing  
We welcome contributions from the community! Whether it's fixing bugs, enhancing documentation, or suggesting features tailored to Indian markets, your input is invaluable. Join our open-source financial AI research community to help shape the future of trading in India.
