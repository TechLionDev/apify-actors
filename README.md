# TechLion Dev — Apify Store Actors

Twenty-three public [Apify](https://apify.com/techliondev) Actors from [TechLion Dev](https://www.techlion.dev). They collect public data (reviews, jobs, leads, catalogs, feeds and archives) with no login to the source sites. Pricing is pay per result plus a $0.00005 start fee, so a first run is usually under a cent. Filters are free.

Directory site: https://actors.techlion.dev

This repository is a directory and a starting point for calling the Actors from your own code. The source that runs on Apify lives on the platform; each Store page has the live README, input schema and pricing.

## Actors

| Actor | Store page | What it does | Typical price |
| --- | --- | --- | --- |
| Google Play Reviews Scraper | https://apify.com/techliondev/google-play-reviews-scraper | Android reviews, ratings, versions, developer replies | $0.05 / 1,000 reviews |
| Apple App Store Reviews Scraper | https://apify.com/techliondev/apple-app-store-reviews-scraper | iOS reviews, ratings and text | $0.05 / 1,000 reviews |
| App Store Scraper | https://apify.com/techliondev/app-store-scraper | Apple app details, search, developer catalogs, top charts | $0.30 / 1,000 apps |
| Trustpilot Reviews Scraper | https://apify.com/techliondev/trustpilot-reviews-scraper | Ratings, replies, verified status, TrustScore | $0.40 / 1,000 reviews |
| Greenhouse Jobs Scraper | https://apify.com/techliondev/ats-job-feed | Greenhouse, Lever, Ashby and Workday job boards | $1.50 / 1,000 jobs |
| Remote Jobs Scraper | https://apify.com/techliondev/remote-jobs-scraper | RemoteOK, We Work Remotely, Himalayas and similar | $0.80 / 1,000 jobs |
| Hacker News Scraper | https://apify.com/techliondev/hacker-news-scraper | Stories, comments, Who Is Hiring | $0.10 / 1,000 items |
| Yellow Pages Scraper | https://apify.com/techliondev/yellow-pages-scraper | US business leads, phones, optional emails | $1.00 / 1,000 businesses |
| BBB Scraper | https://apify.com/techliondev/bbb-business-scraper | Better Business Bureau listings and ratings | $0.80 / 1,000 businesses |
| Contractor License Scraper | https://apify.com/techliondev/contractor-license-scraper | Licensed contractors in WA, OR, TX and NY | $1.00 / 1,000 licenses |
| Website Email & Contact Scraper | https://apify.com/techliondev/website-contact-scraper | Emails, phones and social links from websites | $0.50 / 1,000 pages |
| Email Validator | https://apify.com/techliondev/email-validator | Bulk email checker (MX, disposable, typos) | $0.20 / 1,000 emails |
| Shopify & WooCommerce Products | https://apify.com/techliondev/shopify-woocommerce-products-scraper | Prices, variants and stock | $0.50 / 1,000 products |
| Federal Contracts Scraper | https://apify.com/techliondev/federal-contracts-feed | USAspending and SAM.gov | $2.00 / 1,000 records |
| Luma Events Scraper | https://apify.com/techliondev/luma-events-scraper | lu.ma events, hosts, tickets, guests | $1.50 / 1,000 events |
| ISBN Lookup API | https://apify.com/techliondev/isbn-book-lookup | Book metadata and covers by ISBN or title | $0.50 / 1,000 books found (misses free) |
| Telegram Channel Scraper | https://apify.com/techliondev/telegram-channel-scraper | Channel posts, views and reactions, no login | $0.50 / 1,000 posts |
| Substack Newsletter Scraper | https://apify.com/techliondev/substack-scraper | Posts, full text and comments | $0.50 / 1,000 posts |
| Bluesky Scraper | https://apify.com/techliondev/bluesky-scraper | Posts by search, hashtag, profile or thread | $0.30 / 1,000 posts |
| RSS Feed Reader | https://apify.com/techliondev/rss-feed-reader | RSS, Atom and podcasts to JSON | $0.50 / 1,000 items |
| Sitemap Extractor | https://apify.com/techliondev/sitemap-url-extractor | Every URL in a sitemap, optional SEO check | $0.30 / 1,000 URLs |
| WHOIS Lookup | https://apify.com/techliondev/domain-whois-lookup | Bulk expiry, registrar, availability, DNS | $0.50 / 1,000 domains |
| Wayback Machine Scraper | https://apify.com/techliondev/wayback-machine-scraper | archive.org snapshot history and dates | $0.30 / 1,000 snapshots |

Paid Apify plans get lower per-result prices (Bronze 10% off through Diamond 60% off).

## Call an Actor from code

```javascript
import { ApifyClient } from 'apify-client';

const client = new ApifyClient({ token: process.env.APIFY_TOKEN });
const run = await client.actor('techliondev/isbn-book-lookup').call({
    queries: ['9780141439518', 'To Kill a Mockingbird'],
});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
console.log(items);
```

```python
from apify_client import ApifyClient

client = ApifyClient()  # uses APIFY_TOKEN
run = client.actor("techliondev/isbn-book-lookup").call(run_input={
    "queries": ["9780141439518", "To Kill a Mockingbird"],
})
items = client.dataset(run["defaultDatasetId"]).list_items().items
print(items)
```

Replace the Actor name with any slug from the table. Each Store page has the exact input fields and a sample.

## Links

- Store profile: https://apify.com/techliondev
- Directory: https://actors.techlion.dev
- Company site: https://www.techlion.dev
