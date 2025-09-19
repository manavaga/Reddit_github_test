# Setup Guide for Reddit Crypto Ideas Analyzer

## Quick Start

### Step 1: Prerequisites
- n8n instance (local or cloud)
- Reddit account
- OpenAI account with API access

### Step 2: Get Reddit API Credentials

1. Go to https://www.reddit.com/prefs/apps
2. Click "Create App" or "Create Another App"
3. Fill in:
   - **Name**: n8n Integration
   - **App type**: Script
   - **Description**: n8n workflow automation
   - **About URL**: (leave blank)
   - **Redirect URI**: `http://localhost:5678/rest/oauth2-credential/callback`
   - For n8n cloud: `https://your-instance.app.n8n.cloud/rest/oauth2-credential/callback`
4. Click "Create app"
5. Note your:
   - **Client ID**: Under "personal use script"
   - **Client Secret**: Click "edit" to see it

### Step 3: Get OpenAI API Key

1. Go to https://platform.openai.com/api-keys
2. Click "Create new secret key"
3. Name it "n8n"
4. Copy the key immediately (won't be shown again)

### Step 4: Import Workflow to n8n

1. Copy all content from `reddit_crypto_workflow.json`
2. In n8n:
   - Click "Workflows" → "Add Workflow" → "Import from JSON"
   - Paste the JSON
   - Click "Save"

### Step 5: Configure Credentials in n8n

#### Reddit OAuth2:
1. Go to Credentials → Create New → Reddit OAuth2 API
2. Enter:
   - Client ID: (from Reddit app)
   - Client Secret: (from Reddit app)
3. Click "Connect My Account"
4. Authorize in Reddit
5. Save

#### OpenAI:
1. Go to Credentials → Create New → OpenAI API
2. Enter:
   - API Key: (from OpenAI)
3. Save

### Step 6: Test the Workflow

1. Open the workflow
2. Click "Execute Workflow" or click the Manual Trigger
3. Watch as it:
   - Fetches Reddit posts
   - Filters crypto content
   - Analyzes with AI
   - Returns top 10 ideas

## Troubleshooting

### Reddit Connection Issues

**Error: "invalid redirect_uri"**
- Ensure redirect URI matches exactly
- No trailing slashes
- Correct protocol (http/https)

**Error: "unauthorized"**
- Re-authenticate in n8n
- Check Client ID/Secret

### OpenAI Issues

**Error: "insufficient_quota"**
- Add credits to OpenAI account
- Check API limits

**Error: "model_not_found"**
- Ensure you have access to GPT-4
- Try changing to "gpt-3.5-turbo" in the node

### Merge Node Issues

**Error: "Fields to match required"**
- The workflow is configured correctly with "id" field
- If error persists, change mode to "append"

## Customization

### Change Subreddits
Edit Reddit nodes → "subreddit" parameter

### Add Keywords
Edit "Filter & Analyze Posts" → add to `cryptoKeywords` array

### Adjust Limits
Edit Reddit nodes → "limit" parameter (max 100)

### Change AI Model
Edit "OpenAI Analysis" → "model" parameter
- Options: "gpt-4o-mini", "gpt-3.5-turbo", "gpt-4"

## Support

For help:
1. Check n8n documentation: https://docs.n8n.io
2. Reddit API docs: https://www.reddit.com/dev/api
3. OpenAI docs: https://platform.openai.com/docs
4. Open an issue in this repository