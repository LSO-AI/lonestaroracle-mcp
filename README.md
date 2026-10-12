# LoneStarOracle MCP

Pay-per-call market data for AI agents, served over MCP. No signup, no API key: each tool call is paid in USDC on Base via [x402](https://x402.org), and the price is shown in the payment request before anything is charged.

**Endpoint (Streamable HTTP):** `https://mcp.lonestaroracle.xyz/mcp`

## Tools

| Tool | What it returns | Price |
|---|---|---|
| `token_scan` | Crypto token due diligence: honeypot / rug risk score, ownership, liquidity, holder concentration (EVM or Solana) | $0.15 |
| `equity_signal` | US stock signal: buy / neutral / sell plus upside to the analyst price target | $0.05 |
| `smart_money` | One accumulation / distribution signal for a US stock from insider buys (Form 4), congressional trades, 13F flow and analyst consensus | $0.10 |
| `labor_pulse` | US labor market: payrolls, unemployment, wage growth, JOLTS openings and quits (BLS) | $0.05 |
| `critical_minerals` | Supply concentration, US import reliance and refined vs mined read for a critical mineral (USGS) | $0.05 |
| `wallet_pnl` | Realized / unrealized PnL and trade history for a Base wallet | $0.20 |

## Connect

Any MCP client that supports remote Streamable HTTP servers and an x402 payment hook can use it. Point the client at the endpoint above; on a tool call the server answers with an x402 payment request, the client pays, and the result comes back.

```json
{
  "mcpServers": {
    "lonestaroracle": { "url": "https://mcp.lonestaroracle.xyz/mcp" }
  }
}
```

## More

- 70+ data services (crypto, equities, macro, real-economy, global risk) also available as plain x402 REST endpoints: [docs.lonestaroracle.xyz](https://docs.lonestaroracle.xyz)
- One-fetch catalog: [lonestaroracle.xyz/openapi.json](https://lonestaroracle.xyz/openapi.json)
- Site: [lonestaroracle.xyz](https://lonestaroracle.xyz)

Data, not financial advice.
