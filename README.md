# Global Media Sentiment & Geopolitics (NLP)

An end-to-end NLP pipeline analyzing editorial framing and geopolitical sentiment across major international news outlets during global crises.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1KucWdZADfHib0nxmlgXJnsnXs78O0yGM)

HTML:
<a href="https://colab.research.google.com/drive/12PulltQ_lctKRY4cvoGs_VG4xQD6Lyr7#scrollTo=AsgC2URKu9kd" target="_blank">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

---

## Overview
This project benchmarks media coverage across diverse political blocs (e.g., Western democracies, China, Russia) during international conflicts. By evaluating news headlines through transformer-based sentiment analysis, the pipeline measures emotional polarity and cross-national editorial bias.

## Key Features
* **Transformer-Based NLP:** Uses `cardiffnlp/twitter-roberta-base-sentiment-latest` via Hugging Face `pipeline` for sequence classification (`positive`, `neutral`, `negative`).
* **Geopolitical Benchmarking:** Maps sentiments onto discrete geopolitical factions and government alignments (`Orientamento governo`) to expose narrative discrepancies.
* **Sentiment Metric Normalization:** Translates qualitative model outputs into a continuous polarity index ($+1.0$ positive, $0.0$ neutral, $-1.0$ negative).
* **Interactive Visualization:** Renders dynamic bar charts via `Plotly Express` with custom diverging color scales (`RdBu`) to highlight emotional divergence.
* **Automated Data Pipeline:** Pulls remote tabular datasets directly from GitHub via `pandas` with robust missing-value handling and GPU-accelerated batch inference.

## Tech Stack
* **Language:** Python 3.10+
* **Deep Learning & NLP:** Hugging Face Transformers, PyTorch
* **Data Processing:** Pandas
* **Visualization:** Plotly Express
* **Infrastructure:** Google Colab (T4 GPU)

## Architecture & Workflow
```text
GitHub Raw CSV
      │
      ▼
Pandas Preprocessing (Missing value handling, text normalization)
      │
      ▼
RoBERTa Sentiment Pipeline (GPU-accelerated inference)
      │
      ▼
Sentiment Scoring (-1.0 to +1.0) & Group-by Aggregation
      │
      ▼
Plotly Express Interactive Visualizations
