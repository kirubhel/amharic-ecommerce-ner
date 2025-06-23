## Task 4: Model Comparison & Selection

We fine-tuned three different transformer-based models on our Amharic NER dataset to extract entities such as product names, prices, and locations.

| Model                                       | F1 Score | Precision | Recall | Eval Runtime (s) | Samples/sec | Notes |
|--------------------------------------------|----------|-----------|--------|------------------|-------------|-------|
| `xlm-roberta-base`                         | 1.00     | 1.00      | 1.00   | 0.10             | 9.84        | ⚡ Fastest |
| `bert-tiny-amharic`                        | 1.00     | 1.00      | 1.00   | 0.80             | 1.26        | 🪶 Lightweight |
| `afroxlmr-large-ner-masakhaner-1.0_2.0`    | 1.00     | 1.00      | 1.00   | 2.51             | 0.40        | 🧠 Largest |

Despite all models achieving perfect evaluation metrics on our test set, this is likely due to the small size and simplicity of the dataset, which is prone to overfitting.

### 🔍 Model Recommendation

We recommend **`xlm-roberta-base`** as the best trade-off between performance and inference speed. It provides high accuracy and is more production-ready than larger alternatives, while significantly faster than `afroxlmr`.

---

**Next Step:** We will use the selected model in Task 5 to interpret predictions using SHAP/LIME, and later score vendors in Task 6.
