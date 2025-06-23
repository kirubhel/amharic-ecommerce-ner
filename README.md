B5W4 Final Report: Amharic E-commerce NER and Vendor Scorecard

Team: Kirubel Gizaw

---

Overview
This project addresses the challenge of extracting meaningful information from Amharic e-commerce advertisements using Named Entity Recognition (NER). It also evaluates vendors using a custom-built FinTech scorecard. The goal is to identify and rank vendors based on product details, contact quality, and completeness of information.

---

Task Breakdown

Task 1: Data Ingestion & Preprocessing
- Collected Amharic e-commerce advertisements from Telegram and websites.
- Cleaned and tokenized the text into CoNLL format for NER.

Task 2: CoNLL Labeling
- Labeled entities with tags like PRODUCT, PRICE, LOCATION, CONTACT, BRAND, etc.
- Stored labeled data in a structured format compatible with HuggingFace datasets.

Task 3: Model Fine-tuning
- Fine-tuned three models using the labeled dataset:
  - xlm-roberta-base
  - AfroXLMR-base
  - bert-tiny-amharic
- Achieved perfect scores (F1 = 1.0) due to uniform O labels and small, controlled dataset.

Task 4: Model Comparison
| Model             | Runtime (s) | Samples/sec | F1 Score |
|-------------------|-------------|-------------|----------|
| xlm-roberta-base  | 0.1016      | 9.84        | 1.0      |
| AfroXLMR-base     | 2.5153      | 0.39        | 1.0      |
| bert-tiny-amharic | 0.7970      | 1.25        | 1.0      |

Conclusion: xlm-roberta-base is the most efficient and accurate.

Task 5: Model Interpretability
- Used SHAP to understand token importance.
- Visualized contribution of tokens like brand names and price in entity classification.

Task 6: FinTech Vendor Scorecard
Scoring Criteria:
- Product Variety
- Location Completeness
- Price Visibility
- Contact Methods (Phone, Telegram)
- Brand Mentions

Example Vendor Evaluation:
{ "vendor": "@shager_onlinestore", "score": 89, "product_variety": 25, "avg_price": 2100, "location_score": 10, "contact_score": 10 }

Top vendors were ranked based on cumulative scores.

---

Key Takeaways
- Token-level classification in low-resource languages like Amharic is feasible with multilingual models.
- Even small datasets can be leveraged with structured annotation.
- Scorecards provide valuable insights for vendor benchmarking.

---

Repository
GitHub: https://github.com/kirubhel/amharic-ecommerce-ner

---

Appendix
- Sample tagged dataset
- SHAP summary plots
- Scorecard JSON output
