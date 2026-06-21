---
layout: default
title: Siemens SiePortal Scraper Suite | MPN & Catalog Export
description: Extract Siemens part numbers, specs, lifecycle, SIOS documents and TED datasheets from SiePortal. Apify Actors for BOM audits, procurement and ERP pipelines.
permalink: /
---

# Siemens SiePortal Scraper Suite

**Crawloop** provides production-grade [**Apify Actors**](https://apify.com/crawloop?fpr=guboir) for **Siemens SiePortal** (Industry Mall), **SIOS**, and **TED** product datasheets — structured JSON and CSV export for procurement teams, system integrators, and BOM engineering workflows.

Extract **Siemens part numbers (MPN / MLFB)**, technical specifications, **product lifecycle status**, successor replacements, certificates, manuals, and datasheet PDFs — without manual copy-paste from vendor portals.

[Browse all Actors on Apify](https://apify.com/crawloop?fpr=guboir){: .btn .btn-primary} &nbsp; [Product site on crawloop.com](https://crawloop.com/siemens-automation.html) &nbsp; [View source on GitHub](https://github.com/PLCSPS-DEV/siemens-sieportal-automation)

> **Also from Crawloop Industrial:** [Rockwell Automation Suite](https://crawloop.com/rockwell-automation.html) · [GitHub docs](https://plcsps-dev.github.io/rockwell-automation/)

---

## Siemens catalog Actors on Apify

| Discovery | Enrichment | SIOS documents | TED datasheets |
| :--- | :--- | :--- | :--- |
| [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler?fpr=guboir) | [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper?fpr=guboir) | [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader?fpr=guboir) | [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader?fpr=guboir) |
| | [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker?fpr=guboir) | [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler?fpr=guboir) | [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler?fpr=guboir) |

---

## Siemens automation pipeline

```
Phase 1 — Discover MPNs          Phase 2 — Screen & enrich       Phase 3 — Documents & specs

  Catalog Crawler ──► MPN list ──► Lifecycle Tracker ──► SiePortal Scraper
                                    │
                    ┌───────────────────────────┴───────────────────────────┐
                    ▼                                                       ▼
        Document Downloader (SIOS)                         TED Datasheet Downloader
        certificates, manuals, CAD                          compact catalog PDFs
                    │                                                       │
                    ▼                                                       ▼
        Document PDF Parser                                  TED Datasheet Parser
```

---

## Which Siemens Apify Actor do I need?

| Your goal | Actor |
| :--- | :--- |
| Discover MPNs via keyword or full-catalog crawl | [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler?fpr=guboir) |
| Full specs, lifecycle, document links, accessories by MPN | [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper?fpr=guboir) |
| Bulk BOM lifecycle and successor part numbers | [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker?fpr=guboir) |
| Download CE / UL / manual PDFs from SIOS | [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader?fpr=guboir) |
| Parse specs from SIOS / manual PDFs | [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler?fpr=guboir) |
| Download official TED product datasheet PDF | [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader?fpr=guboir) |
| Parse TED PDFs to structured JSON (no browser) | [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler?fpr=guboir) |

### SIOS vs TED PDF pipelines

| Pipeline | Source | Download | Parse |
| :--- | :--- | :--- | :--- |
| **SIOS** | Manuals, certificates, engineering files | [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader?fpr=guboir) | [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler?fpr=guboir) |
| **TED** | Industry Mall product datasheet | [TED Downloader](https://apify.com/crawloop/siemens-datasheet-downloader?fpr=guboir) | [TED Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler?fpr=guboir) |

---

## Use cases

### Siemens BOM obsolescence audit

Run the [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker?fpr=guboir) on your full MPN list. Filter discontinued parts and official successors. Enrich replacement parts with the [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper?fpr=guboir).

### Procurement catalog export

Discover Siemens part numbers with the [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler?fpr=guboir). Export deduplicated MPNs with product detail page URLs for ERP or PIM import.

### Compliance documentation

Download certificates and manuals via the [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader?fpr=guboir). Extract specification tables with the [Document PDF Parser](https://apify.com/crawloop/siemens-sieportal-product-document-pdf-crawler?fpr=guboir).

### High-volume TED datasheet extraction

[TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader?fpr=guboir) → [TED Datasheet Parser](https://apify.com/crawloop/siemens-datasheet-pdf-crawler?fpr=guboir). HTTP download plus parse-only chain — no browser on the parse step.

---

## Pricing

Pay-per-event on Apify. Billed only for successful results — not for `NOT_FOUND` or `FAILED` rows.

| Actor group | Typical price |
| :--- | :--- |
| SiePortal Scraper, Catalog Crawler, Lifecycle Tracker, Document Downloader | from **$5 / 1,000** results |
| TED Datasheet Downloader | **$2 / 1,000** PDFs |
| TED / Document PDF Parser (parse-only) | **$2 / 1,000** PDFs |

Exact pricing is shown on each Actor page before you run.

---

## Quick start

1. Create a free [Apify account](https://apify.com/?fpr=guboir).
2. Open an Actor from the table above.
3. Paste Siemens part numbers (MPNs) or search keywords.
4. Download results as JSON, CSV, or PDFs from Key-Value Store.

**Lifecycle check example** — run on [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker?fpr=guboir):

```json
{
  "searchTerms": ["6GK7343-1EX11-0XE0"],
  "locale": "en-nl",
  "maxConcurrency": 1,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

**Full product record** — run on [SiePortal Scraper](https://apify.com/crawloop/siemens-sieportal-scraper?fpr=guboir):

```json
{
  "searchTerms": ["6ES7193-6BP00-0DA0"],
  "maxResultsPerSearch": 1,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

---

## API integration

All Actors support the [Apify API](https://docs.apify.com/api/v2) and `apify-client` (Python / JavaScript).

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

## Frequently asked questions

### What is a Siemens SiePortal scraper?

A Siemens SiePortal scraper automates extraction of product data from the Siemens Industry Mall / SiePortal catalog — part numbers, specifications, lifecycle status, and document links — into structured JSON or CSV for downstream ERP, PIM, or analytics systems.

### How do I export Siemens part numbers (MPN)?

Use the [Catalog Crawler](https://apify.com/crawloop/siemens-sieportal-product-catalog-crawler?fpr=guboir) for keyword search (`6ES`, `SIMATIC`, …). Both output deduplicated MPN lists with product detail URLs.

### How do I check Siemens product lifecycle and successor parts?

The [Lifecycle Tracker](https://apify.com/crawloop/siemens-sieportal-product-lifecycle-tracker?fpr=guboir) bulk-checks lifecycle phase (Active, Phase-out, Discontinued) and official successor MPNs — faster and lower cost than scraping full product pages.

### Can I download Siemens datasheet PDFs automatically?

Yes. **SIOS** manuals and certificates: [Document Downloader](https://apify.com/crawloop/siemens-sieportal-document-downloader?fpr=guboir). **TED** compact catalog datasheets: [TED Datasheet Downloader](https://apify.com/crawloop/siemens-datasheet-downloader?fpr=guboir). Parse PDFs to JSON with the matching Parser Actor.

### Is this official Siemens software?

No. These are unofficial integrations by [Crawloop](https://apify.com/crawloop?fpr=guboir). Not affiliated with, sponsored by, or endorsed by Siemens AG.

---

## About Crawloop

[Crawloop](https://apify.com/crawloop?fpr=guboir) builds Apify Actors for **industrial automation catalog data** — vendor portals, part numbers, lifecycle, documents, and structured specs. Part of a growing suite covering Siemens, Rockwell Allen-Bradley, and other OEM catalogs.

**Product site:** [crawloop.com/siemens-automation](https://crawloop.com/siemens-automation.html) · **Related suite:** [Rockwell Automation](https://crawloop.com/rockwell-automation.html) · [GitHub docs](https://plcsps-dev.github.io/rockwell-automation/)

Custom enterprise Actors or scheduled runs: contact via [Apify Store](https://apify.com/crawloop?fpr=guboir) or [open an issue](https://github.com/PLCSPS-DEV/siemens-sieportal-automation/issues).

---

> **Disclaimer:** Unofficial integrations developed independently of Siemens AG. Not affiliated with, sponsored by, or endorsed by Siemens AG or its subsidiaries. **Siemens**, **SiePortal**, **SIMATIC**, and related names are trademarks of Siemens AG. Product data is read from publicly accessible Siemens web sources only. Provided for **informational and research purposes only**. You are responsible for compliance with applicable laws and Siemens terms of use. No warranty; use at your own risk.
