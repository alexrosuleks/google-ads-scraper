# Google Ads Scraper: Adstransparency Scraper API for Python & Node.js (2026)

Scrape the Google Ads Transparency Center by advertiser or domain: ad creatives, formats, regions and first and last shown dates. Export to JSON or CSV.

**[▶ Try the Google Ads Scraper free on Scrapely](https://scrape.ly/store/querystone/google-ads-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Adstransparency data with the [Google Ads Scraper](https://scrape.ly/store/querystone/google-ads-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the adstransparency scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Adstransparency scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/querystone/google-ads-scraper) or from your code with the SDK.
- **Structured adstransparency data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $1.17 per 1,000 ad results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Adstransparency changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Adstransparency data can you extract?

Scrape the Google Ads Transparency Center by advertiser or domain: ad creatives, formats, regions and first and last shown dates. Export to JSON or CSV.

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('querystone/google-ads-scraper').call({"startUrls": [{"url": "https://adstransparency.google.com/advertiser/AR08888592736429539329?authuser=0&region=CH&preset-date=Last+30+days"}], "resultsLimit": 10, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('querystone/google-ads-scraper').call(run_input={ "startUrls": [ { "url": "https://adstransparency.google.com/advertiser/AR08888592736429539329?authuser=0&region=CH&preset-date=Last+30+days" } ], "resultsLimit": 10, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/querystone~google-ads-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "startUrls": [
    {
      "url": "https://adstransparency.google.com/advertiser/AR08888592736429539329?authuser=0&region=CH&preset-date=Last+30+days"
    }
  ],
  "resultsLimit": 10,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Google Ads Scraper page](https://scrape.ly/store/querystone/google-ads-scraper).

## Pricing

**$1.17 per 1,000 ad results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/querystone/google-ads-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Adstransparency with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Adstransparency with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a adstransparency scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/querystone~google-ads-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Adstransparency legal?** This scraper collects publicly available data. Check Adstransparency's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** google ads scraper, adstransparency scraper, adstransparency scraper api, adstransparency scraper python, adstransparency scraper node.js,
scrape adstransparency, adstransparency data extraction, adstransparency crawler, adstransparency api, export adstransparency data to csv, google-ads-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/querystone/google-ads-scraper).
