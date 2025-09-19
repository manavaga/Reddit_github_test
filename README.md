# Reddit Crypto Ideas Analyzer - n8n Workflow

## Overview
This n8n workflow automatically fetches and analyzes the top cryptocurrency discussions from Reddit to identify the 10 most promising crypto ideas, trends, and opportunities.

## Features
- 📊 Fetches hot posts from r/CryptoCurrency and r/CryptoMarkets
- 🔍 Filters posts using comprehensive crypto keywords
- 📈 Ranks posts by engagement (upvotes + comments × 3)
- 🤖 Uses OpenAI GPT-4 to analyze and identify top 10 crypto ideas
- 📋 Provides sentiment analysis and risk assessment for each idea

## Quick Start
1. Import `reddit_crypto_workflow.json` into n8n
2. Configure Reddit OAuth2 and OpenAI credentials
3. Run the workflow manually or schedule it

## Prerequisites
- n8n instance (v1.101.2+)
- Reddit OAuth2 API credentials
- OpenAI API key with GPT-4 access

## Installation
See [SETUP.md](SETUP.md) for detailed setup instructions.

## Output Format
```json
{
  "success": true,
  "timestamp": "2025-09-19T...",
  "top_10_crypto_ideas": [
    {
      "name": "Bitcoin",
      "reason": "...",
      "sentiment": "Bullish",
      "risk": "Medium",
      "takeaway": "..."
    }
  ]
}
```

## Repository Contents
- `reddit_crypto_workflow.json` - The n8n workflow file
- `README.md` - This file
- `SETUP.md` - Detailed setup guide
- `LICENSE` - MIT License

## Support
For issues or questions, please open an issue in this repository.

## License
MIT License - Feel free to modify and use as needed.