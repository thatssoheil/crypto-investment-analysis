---
name: crypto-market-analysis-skill
description: Use when user asks for crypto market analysis.
category: research
tags: [crypto, bitcoin, ethereum, market-analysis, on-chain, api-fallbacks]
---

# Crypto Market Analysis Skill

Public API fallback chain when Binance is geo-blocked or unavailable.

## Data Sources (priority order)

### 1. CoinGecko (primary — no API key, reliable)
- Live ticker: `simple/price?ids=bitcoin&vs_currencies=usd&include_24hr_change=true&include_24hr_vol=true&include_market_cap=true`
- 90d prices: `coins/bitcoin/market_chart?vs_currency=usd&days=90` → returns `{prices: [[ts,price],...], total_volumes: [...], market_caps: [...]}`
- 30d OHLC: `coins/bitcoin/ohlc?days=30&vs_currency=usd` → returns `[ts,open,high,low,close]`
- Full coin data: `coins/bitcoin?localization=false&tickers=false&community_data=false&developer_data=true` → includes supply, ATH, dev stats
- ETH/BTC ratio: `coins/ethereum/market_chart?vs_currency=btc&days=90`
- Global data: `global` → total market cap, BTC/ETH dominance, active cryptos, total volume
- Stablecoin mcap: `coins/tether/market_chart?vs_currency=usd&days=7` (USDC too)

**Rate limit**: ~30 req/min. If hit, add delay between calls.

### 2. Alternative.me (Fear & Greed Index)
- `https://api.alternative.me/fng/?limit=7` → returns `{data: [{value, value_classification, timestamp}]}`
- No API key needed.
- Values: 0-25 Extreme Fear, 26-46 Fear, 47-54 Neutral, 55-74 Greed, 75-100 Extreme Greed

### 3. Blockchain.info (network fundamentals)
- Difficulty: `https://blockchain.info/q/getdifficulty`
- 24h tx count: `https://blockchain.info/q/24hrtransactioncount`
- Hashrate: `https://blockchain.info/q/hashrate` (returns raw, divide by 1e18 for EH/s)
- 24h BTC sent: `https://blockchain.info/q/24hrbtcsent`

### 4. Mempool.space (fee market, mempool state)
- Fee estimates: `https://mempool.space/api/v1/fees/recommended` → returns sat/vB for various priorities
- Mempool state: `https://mempool.space/api/mempool` → count, vSize
- Block extras: `https://mempool.space/api/v1/mining/blocks/extras?count=5`

## Multilingual Support (Farsi/Persian)
When the user's preference or input language is Farsi (Persian), provide the analysis in **Modern Fluent Farsi** using professional financial terminology. Use the following Farsi-English mappings for headers and concepts:
- **Live Snapshot:** نمای لحظه‌ای بازار (Live Snapshot)
- **Price Structure:** ساختار قیمت (Price Structure)
- **Key Levels:** سطوح کلیدی (حمایت و مقاومت)
- **On-Chain Dashboard:** داشبورد داده‌های آن‌چین
- **Scenarios:** سناریوهای احتمالی (Scenarios)

### Farsi Market Terminology
- **Whale:** نهنگ (Nahang)
- **Liquidity:** نقدینگی (Naghdinegi)
- **Resistance/Support:** مقاومت / حمایت
- **Breakout:** شکست (Breakout)
- **Volatility:** نوسان‌پذیری

## Analysis Structure

When user asks for full analysis, produce this shape:

### 1. Live Snapshot
Price, 24h change, 24h range, today open, 24h volume, market cap

### 2. Price Structure (30d OHLC)
Bullet summary of key periods: downtrend → rally → consolidation → latest action

### 3. Key Levels
Current support/resistance zones, major resistance, major support (90d floor)

### 4. ETH/BTC Ratio (if ETH is in scope)
Compare 90d high/low/current. Signal: flat = ETH is follower, rising = rotation into ETH, falling = capital fleeing to BTC

### 5. ATH Comparison
Current vs ATH for both BTC and ETH. Shows relative recovery stage.

### 6. On-Chain Dashboard
- Network Health: difficulty, tx count, fee market, hashrate
- Capital Flows: BTC & ETH dominance, stablecoin mcap trends
- Sentiment: Fear & Greed
- Volume Analysis: current vol vs 30d avg (vol ratio)

### 7. Scenarios
Bullish (prob), Neutral (prob), Bearish (prob) — each with trigger levels and targets
- **Note:** If responding in Farsi, maintain a professional, analytical tone (Senior Analyst level).

## Pitfalls
- **Binance is geo-blocked** from this location. Don't attempt binance.com API. Use CoinGecko as primary.
- **blockchain.info** endpoints return raw unformatted numbers. Divide hashrate by 1e18 for EH/s.
- **CoinMetrics** requires an API key for most endpoints. Skip unless key is configured.
- **btc.com API** is unreliable (frequent timeouts). Don't depend on it.
- **Coinbase API** (`api.coinbase.com/v2/prices/BTC-USD/spot`) works for spot price but no detailed data.
- **OKX/Binance funding rates** often time out from restricted regions. Not guaranteed.
- When user provides their own position info (entry price, amount held), calculate:
  - Current position P&L (value now vs cost basis)
  - What new buy at current price does to average cost
  - Breakeven price after averaging down
