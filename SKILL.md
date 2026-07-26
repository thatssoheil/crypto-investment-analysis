---
name: crypto-investment-analysis
description: Crypto investment analysis for various time horizons.
---

# crypto-investment-analysis

Use this skill to conduct a professional, institutional-grade analysis of any cryptocurrency for both short-term trading and long-term holding.

## Trigger Conditions
- User asks for an analysis of a specific coin (e.g., "Analyze SOL", "Look into ZEC").
- User asks for a "deep dive" or "professional outlook" on a crypto asset.
- User wants to know if a coin is a good investment right now.

## Procedure

### 1. Layer 1: Macro & Market Sentiment (The Wind)
- **Check BTC Dominance (BTC.D):** Use `api.coingecko.com/api/v3/global`. High BTC.D (>55%) = BTC is the safe play. Falling BTC.D = Altseason potential.
- **Fear & Greed Index:** Use `api.alternative.me/fng/`. Buy in Fear (<30), Caution/Sell in Greed (>70).
- **Stablecoin Liquidity:** Check USDT/USDC market cap trends. Growing caps = new liquidity entering the market.

### 2. Layer 2: Fundamental Analysis (The Engine)
- **Tokenomics:** Check circulating vs. max supply. High circulating % is safer (less dilution from unlocks).
- **Utility:** Define the core problem the coin solves (Privacy, L1, Oracle, etc.).
- **Developer Activity:** Use `developer_data` from CoinGecko. Check 4-week commit counts and stars.
- **Social Dominance:** Assess if the coin is currently "over-hyped" or "under-noticed."

### 3. Layer 3: On-Chain Data (The Truth)
- **Network Health:** Check Hashrate/Difficulty (for PoW) or Staking Ratio (for PoS).
- **Transaction Activity:** Check daily transactions (TxCnt) and Active Addresses (AdrActCnt) via available explorers or APIs.
- **Exchange Flows:** Use tickers and exchange volume to see if liquidity is concentrating or dispersing.
- **MVRV Ratio:** If available, check Market Value vs. Realized Value. MVRV < 1 is usually a long-term bottom.

### 4. Layer 4: Technical Analysis (The Entry)
- **Price Structure:** Identify 90-day and 1-year Highs/Lows. Is the trend making Higher Highs?
- **Relative Strength ([Coin]/BTC):** Calculate the ratio of the coin price to BTC price. Is the coin outperforming Bitcoin?
- **Key Levels:** Define immediate support, major floor, and primary resistance targets.
- **Volume Profile:** Check if volume is declining on pullbacks (bullish) or spiking on sells (bearish).

## Ahead Scenarios
Always provide three scenarios:
1. **Bullish Continuation:** Clear trigger (e.g., break of $X resistance) and target.
2. **Neutral/Consolidation:** Range boundaries and expected duration.
3. **Bearish Retest:** Invalidation points and support floors.

## Output Format
- **Executive Summary:** Quick stats and current price.
- **The 4-Layer Breakdown:** Clear, concise findings for each layer.
- **The "Pro" Verdict:** Final recommendation (Buy/Hold/Wait).
- **DCA/Exit Plan:** Specific price levels for entries and profit-taking.

## Pitfalls
- **USD Bias:** Never ignore the [Coin]/BTC ratio. A coin going up in USD but down in BTC is a "losing" trade.
- **Ignore the Macro:** Don't buy a "good" altcoin if BTC is breaking down from a major support.
- **Ignoring Dilution:** Always check for upcoming token unlocks (Layer 2).
