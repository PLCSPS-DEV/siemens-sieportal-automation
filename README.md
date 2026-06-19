# Crawloop Siemens Automation Suite

Structured data extraction for **Siemens SiePortal** (Industry Mall), **SIOS**, and **TED** product datasheets. Built for procurement teams, system integrators, and BOM engineering workflows.

All actors run on [Apify](https://apify.com/crawloop) — serverless, API-ready, pay-per-result.

> **Disclaimer:** These are unofficial integrations developed independently of Siemens AG. They are not affiliated with, sponsored by, or endorsed by Siemens AG or any of its subsidiaries.

---

## Actors

| Discovery | Enrichment | SIOS documents | TED datasheets |
| :--- | :--- | :--- | :--- |
| [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler) | [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper) | [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader) | [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader) |
| [Category Scraper](https://apify.com/crawloop/siemens-category-scraper) | [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker) | [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler) | [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler) |

---

## Pipeline

```
Phase 1 — Discover MPNs          Phase 2 — Screen & enrich       Phase 3 — Documents & specs
─────────────────────────          ─────────────────────────       ─────────────────────────────

  Catalog Crawler  ──┐
                      ├──► MPN list ──► Lifecycle Tracker ──► SiePortal Scraper
  Category Scraper ──┘                          │
                                                 │
                    ┌────────────────────────────┴────────────────────────────┐
                    │                                                          │
                    ▼                                                          ▼
        Document Downloader (SIOS)                              TED Datasheet Downloader
        certificates, manuals, CAD                               compact catalog PDFs
                    │                                                          │
                    ▼                                                          ▼
        Document PDF Parser                                       TED Datasheet Parser
        specs from SIOS PDFs                                     specs from TED PDFs
```

---

## Which actor do I need?

| Your goal | Start here |
| :--- | :--- |
| Find Siemens part numbers by keyword (`6ES`, `SIMATIC`, `S7-1200`) | [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler) |
| Export all MPNs under a SiePortal category branch | [Category Scraper](https://apify.com/crawloop/siemens-category-scraper) |
| Full product specs, lifecycle, document links, accessories — by MPN | [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper) |
| Bulk BOM check: lifecycle phase + successor MPNs (fast, low cost) | [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker) |
| Download CE/UL/manual PDFs from SIOS to Key-Value Store | [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader) |
| Extract structured specs from SIOS/manual PDFs | [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler) |
| Download official TED catalog datasheet PDF (1 MLFB → 1 PDF) | [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader) |
| Parse TED PDFs into JSON specs (no browser) | [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler) |

### Two PDF pipelines — do not mix them up

| Pipeline | Source | Download | Parse |
| :--- | :--- | :--- | :--- |
| **SIOS** | Manuals, certificates, engineering files | [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader) | [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler) |
| **TED** | Compact Industry Mall product datasheet | [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader) | [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler) |

---

## Use cases

**BOM obsolescence audit** — Run [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker) on your full MPN list. Filter discontinued parts and successors. Enrich only replacements with [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper).

**Procurement catalog build** — Discover MPNs with [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler) or [Category Scraper](https://apify.com/crawloop/siemens-category-scraper). Export deduplicated part numbers with PDP URLs for ERP import.

**Compliance documentation pack** — Download certificates and manuals via [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader). Parse specification tables with [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler).

**High-volume datasheet extraction** — [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader) → [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler). HTTP download + parse-only chain, no browser on the parse step.

---

## Pricing overview

Pay-per-event on Apify. You are billed only for successful results — not for `NOT_FOUND` or `FAILED` rows.

| Actor | Typical price |
| :--- | :--- |
| SiePortal Scraper, Catalog Crawler, Category Scraper, Lifecycle Tracker, Document Downloader | from **$5 / 1,000** results |
| TED Datasheet Downloader | **$2 / 1,000** downloaded PDFs |
| TED Datasheet Parser, Document PDF Parser (parse-only) | **$2 / 1,000** parsed PDFs |

Exact pricing is shown on each Actor page in Apify Store before you run.

---

## Quick start

1. Create a free [Apify account](https://apify.com/?fpr=crawloop).
2. Open the Actor you need from the table above.
3. Paste your Siemens part numbers (MPNs) or search keywords into the input form.
4. Run — results appear in Dataset (JSON/CSV) or Key-Value Store (PDFs).

**Example — check one MPN lifecycle:**

```json
{
  "searchTerms": ["6GK7343-1EX11-0XE0"],
  "locale": "en-nl",
  "maxConcurrency": 1,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

Run on: [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker)

**Example — full product record:**

```json
{
  "searchTerms": ["6ES7193-6BP00-0DA0"],
  "maxResultsPerSearch": 1,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

Run on: [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper)

---

## API integration

All actors support the [Apify API](https://docs.apify.com/api/v2) and official clients (`apify-client` for Python/JS). Each Actor page includes copy-paste API examples.

```bash
pip install apify-client
```

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("crawloop/siemens-sieportal-product-lifecycle-tracker").call(
    run_input={"searchTerms": ["6GK7343-1EX11-0XE0"], "proxyConfiguration": {"useApifyProxy": True}}
)
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item["lifecyclePhase"], item.get("successors"))
```

---

## About Crawloop

[Crawloop](https://apify.com/crawloop) builds production-grade web data actors for industrial automation and other verticals. Actor source code is proprietary; this repository is the public product hub and documentation index.

Questions or custom enterprise runs: open an issue in this repository or contact via Apify Store.

---

## Repository structure

This repo contains **marketing and documentation only**. Actor source code is deployed privately to Apify Cloud.

| Path | Purpose |
| :--- | :--- |
| `README.md` | This page — suite overview |
| `docs/` | GitHub Pages site (same content) |
