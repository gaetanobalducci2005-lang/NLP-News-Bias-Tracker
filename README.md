# Live News Ingestion Module (`feature/live-news-scraping`)

A lightweight ingestion component for the **NLP News Bias Tracker** that transitions the project from static CSV datasets to on-demand, real-time news scraping using the Google News API.

---

## Overview
This module enables dynamic headline querying across international press outlets. Instead of relying on pre-compiled historical data, it queries current media coverage based on user-defined keywords (e.g., `"Trump"`, `"Iran"`, `"Geopolitics"`) and structures the output for sentiment evaluation.

## Key Features
* **Keyword-Driven Search:** Retrieve active media coverage across publishers matching specific query parameters.
* **Configurable Scraping Filters:** Set publication windows (`period`), result limits (`max_results`), target regions (`country`), and language (`language`).
* **Zero-Result Handling:** Built-in validation that flags empty search returns gracefully.
* **Pipeline-Ready Output:** Formats scraped results (article title, source URL, publisher) for seamless ingestion into downstream `transformers` sentiment pipelines.

## Requirements & Installation
Install the required dependency:

```bash
pip install gnews
