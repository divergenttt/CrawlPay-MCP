# @crawlpay/mcp-server

CrawlPay MCP server for Claude Desktop, Cursor, Windsurf.

Automatically pays $0.001 USDC per page when an AI agent 
encounters a CrawlPay-protected paywall.

## Setup

Add to your Claude Desktop config:

```json
{
  "mcpServers": {
    "crawlpay-server": {
      "command": "npx",
      "args": ["-y", "@crawlpay/mcp-server"],
      "env": {
        "CRAWLPAY_API_KEY": "cr_live_YOUR_KEY_HERE"
      }
    }
  }
}
```

Config file location:
- Windows: `%APPDATA%\Claude\claude_desktop_config.json`
- Mac: `~/Library/Application Support/Claude/claude_desktop_config.json`

## Get API key

1. Go to crawl-pay.com/connect/api-keys
2. Sign in with Google or GitHub
3. Fund your wallet with USDC on Base
4. Generate API key
5. Paste it into config above

## Tool

`handle_payment_required`
- url: URL that returned 402
- amount: USDC amount (default "0.001")

## How it works

```
Agent reads a CrawlPay-protected page
→ Gets HTTP 402 Payment Required
→ MCP server intercepts
→ Pays $0.001 USDC on Base automatically
→ Content unlocked
```

## Links

- [crawl-pay.com](https://crawl-pay.com)
- [github.com/divergenttt/CrawlPay-Vault](https://github.com/divergenttt/CrawlPay-Vault)
- npm: coming soon

*Built on Base · Circle · Privy*
