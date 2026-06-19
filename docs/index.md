---
title: Crawloop Siemens Automation Suite
description: Apify actors for Siemens SiePortal MPN discovery, lifecycle checks, SIOS documents, and TED datasheet extraction.
---

# Crawloop Siemens Automation Suite

Structured data extraction for **Siemens SiePortal** (Industry Mall), **SIOS**, and **TED** product datasheets.

[View full documentation on GitHub](https://github.com/PLCSPS-DEV/siemens-sieportal-automation#readme) · [Apify Store — Crawloop](https://apify.com/crawloop)

> **Disclaimer:** Unofficial integrations. Not affiliated with, sponsored by, or endorsed by Siemens AG.

## Actors

| Discovery | Enrichment | SIOS documents | TED datasheets |
| :--- | :--- | :--- | :--- |
| [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler) | [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper) | [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader) | [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader) |
| [Category Scraper](https://apify.com/crawloop/siemens-category-scraper) | [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker) | [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler) | [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler) |

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
