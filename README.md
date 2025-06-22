# Amharic E-commerce Named Entity Recognition

This project is part of 10 Academy's B5W4 Challenge: Building an Amharic E-commerce Data Extractor. The goal is to extract structured entities such as product names, prices, and locations from Amharic-language e-commerce messages posted on Telegram.

## 🔍 Objective

To fine-tune a Named Entity Recognition (NER) model that can extract:
- 🛍️ Product Names
- 💰 Prices
- 📍 Locations

from Amharic text data collected from Ethiopian Telegram vendors.

---

## ✅ Tasks Completed (Interim)

### Task 1: Data Ingestion & Preprocessing
- Collected messages from 5 real Telegram e-commerce channels:
  - `@Shageronlinestore`, `@ZemenExpress`, `@Leyueqa`, `@helloomarketethiopia`, `@nevacomputer`
- Used `Telethon` for asynchronous scraping.
- Saved messages and media into structured format: `telegram_data.csv` + product photos.

### Task 2: CoNLL Labeling
- Extracted 30+ Amharic messages for manual annotation.
- Created CoNLL file: `data/labeled/ner_sample.conll`
- Tokens are tagged with `B-Product`, `I-PRICE`, `B-LOC`, etc.

---

## 📁 Project Structure

```
amharic-ecommerce-ner/
├── data/
│   ├── raw/                # Scraped Telegram messages & media
│   └── labeled/            # CoNLL-formatted NER training data
├── scripts/
│   └── telegram_scraper.py # Telethon scraper
├── notebooks/
│   └── preprocessing.ipynb # Amharic text cleaning
└── interim_report.pdf      # 1-2 page progress report
```

---

## 📌 Next Steps

- Fine-tune models using Hugging Face (XLM-Roberta, mBERT)
- Evaluate & compare NER performance
- Use SHAP/LIME to explain predictions
- Build Fintech Vendor Scorecard using engagement data

---

## 👨‍💻 Author
Kirubel Gizaw
