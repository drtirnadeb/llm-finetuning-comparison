
## 🔍 DistilBERT Sentiment Fine-Tuning: Classifier-Only vs. Partial Unfreezing

This project explores two strategies for fine-tuning a pretrained transformer (`distilbert-base-uncased`) on a binary sentiment classification task using the [Yelp Polarity dataset](https://huggingface.co/datasets/yelp_polarity):

- **Model 1**: Fine-tunes **only the final classification layer**
- **Model 2**: Also fine-tunes the **last encoder layer** of the transformer

We compare the two models in terms of **validation accuracy**, **loss**, and **F1 score**, and examine how unfreezing the encoder improves prediction confidence.

---

## 📊 Results Overview

| Metric           | Model 1 (Classifier Only) | Model 2 (+Last Encoder Layer) |
|------------------|---------------------------|-------------------------------|
| Validation Accuracy | ~87%                    | **~92%**                      |
| Validation F1 Score | (plotted)               | (plotted)                     |
| Confidence (example) | 84.6% / 75.7%           | **99.9% / 99.5%**             |

✅ Model 2 consistently shows stronger confidence and slightly better generalization.

---

## 🧠 Key Concepts Demonstrated

- Hugging Face Transformers (`Trainer`, `TrainingArguments`)
- Tokenization and dataset preparation with `datasets`
- Fine-tuning with frozen and partially unfrozen layers
- Custom evaluation metrics (accuracy + F1)
- Predictions on custom text inputs
- Comparative visualization of model performance

---

## 🧪 Example Predictions

| Input Review | Model 1 | Model 2 |
|--------------|---------|---------|
| _"The food was fantastic and the service was quick."_ | Positive (84.6%) | **Positive (99.9%)** |
| _"It was a waste of money. Worst place ever."_ | Negative (75.7%) | **Negative (99.5%)** |
| _"Mediocre experience. Not terrible, but not great either."_ | Positive (56.4%) | **Negative (88.2%)** |

✅ Both models agree in most cases, but **Model 2 is significantly more confident** and better handles subtle inputs.

