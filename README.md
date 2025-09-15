# 🤖 AI-Powered Crypto Trading Bot

An **AI-driven Ethereum trading bot** that integrates **machine learning price prediction**,  
**Capital.com trading API (demo/live)**, and a **Telegram bot interface** with inline controls.  

---

## ✅ Features
- **ML Model (LSTM)**: Predicts ETH price direction using Binance OHLC data.
- **Live/Demo Trading**: Supports both **Capital.com live** and **demo** modes.
- **Telegram Bot UI**: Inline buttons for opening/closing trades with confirmation.
- **Position Tracking**: Keeps track of open/closed trades in SQLite.
- **AED Conversion**: All trade values shown in **AED** with real-time conversion.
- **Custom Investment**: Choose preset or custom AED investment amounts.
- **Safe Execution**: Bot only trades on explicit Telegram confirmation.

---

## 🛠 Tech Stack
- **Language**: Python 3
- **ML Framework**: PyTorch
- **Data Feed**: Binance API
- **Broker**: Capital.com API
- **Messaging**: Telegram Bot API
- **Database**: SQLite
- **Libraries**:
  - `torch`, `numpy`, `pandas`
  - `python-telegram-bot`
  - `binance`
  - `python-dotenv`
  - `requests`

---

## 📂 Project Structure
     CryptoTradingBot/
     ├── main.py # Main trading bot logic
     ├── trades.db # SQLite DB (auto-created)
     ├── price_predictor.pt # Trained LSTM model (optional)
     ├── requirements.txt # Python dependencies
     ├── .env # Secrets/config (ignored in Git)
     ├── .gitignore
     └── README.md

---

## ⚙️ Setup

### **1. Clone the Repository**
```bash
git clone https://github.com/EbrahimAR/CryptoTradingBot.git
cd CryptoTradingBot
```

### **2. Install Dependencies**
```bash
pip install -r requirements.txt
```

### **3. Configure Environment**
```bash
# Capital.com
CAPITAL_API_KEY=your_capital_api_key
CAPITAL_EMAIL=your_email
CAPITAL_PASSWORD=your_password
CAPITAL_EPIC=ETHUSD

# Telegram
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_CHAT_ID=your_telegram_chat_id

# Trading Settings
# Default fallback values (used only if no AED input is provided in Telegram).
# Actual trade size is chosen interactively in AED via Telegram buttons.
TRADE_AMOUNT_ETH=0.05
TRADE_SYMBOL=ETH/USD
```

### **4. Run the Bot**
```bash
python main.py
```

---

## ▶️ Usage
- `/show` → Run AI prediction, get trading recommendation, choose BUY/SELL.
- `/status` → Show current open trade details and PnL.
- `/close` → Close the last open trade.
- `/capital` → Show Capital.com connection status.
- `/symbols` → Suggest valid ETH epic formats.

⚠️ **Note on trade size**:  
Even though `.env` has a fallback like `TRADE_AMOUNT_ETH=0.05`,  
the **real trade size** comes from your **AED amount** selected in Telegram.  
This ensures you always trade in your preferred local currency.

---

## 🔗 Future Enhancements
- Add Stop Loss / Take Profit directly from Telegram UI.
- Multi-asset support (BTC, SOL, etc.).
- Web dashboard for trade monitoring.
- Strategy backtesting and optimization.

---

## 👨‍💻 Author
Ebrahim Abdul Raoof

[LinkedIn](https://www.linkedin.com/in/ebrahim-ar/) | [GitHub](https://github.com/EbrahimAR)

---

## 📜 License
This project is licensed under the MIT License. See [LICENSE](https://github.com/EbrahimAR/AI-Powered-Crypto-Trading-Bot/blob/main/LICENSE) for details.
