---
title: Crawloop Siemens Automation Suite
description: Apify actors for Siemens SiePortal MPN discovery, lifecycle checks, SIOS documents, and TED datasheet extraction.
---

# Crawloop Siemens Automation Suite

Structured data extraction for **Siemens SiePortal** (Industry Mall), **SIOS**, and **TED** product datasheets.

[View full documentation on GitHub](https://github.com/PLCSPS-DEV/siemens-sieportal-automation#readme) · [Apify Store — Crawloop](https://apify.com/crawloop?fpr=guboir)

> **Disclaimer:** Unofficial integrations. Not affiliated with, sponsored by, or endorsed by Siemens AG. Provided for informational and research purposes only; use at your own risk and comply with applicable terms of use.

## Actors

| Discovery | Enrichment | SIOS documents | TED datasheets |
| :--- | :--- | :--- | :--- |
| [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler?fpr=guboir) | [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper?fpr=guboir) | [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader?fpr=guboir) | [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader?fpr=guboir) |
| [Category Scraper](https://apify.com/crawloop/siemens-category-scraper?fpr=guboir) | [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker?fpr=guboir) | [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler?fpr=guboir) | [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler?fpr=guboir) |

## Pipeline

```
  Catalog Crawler / Category Scraper
              │
              ▼
         MPN list
              │
              ▼
      Lifecycle Tracker ──► SiePortal Scraper
              │
              ├─► Document Downloader ──► Document PDF Parser  (SIOS)
              │
              └─► TED Datasheet Downloader ──► TED Datasheet Parser
```

See the [full README](https://github.com/PLCSPS-DEV/siemens-sieportal-automation#which-actor-do-i-need) for use cases, pricing, and API examples.
