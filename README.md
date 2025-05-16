

# 🤖 Fine-Tuning DistilBERT for Sentiment Classification

This project explores fine-tuning strategies for a transformer-based language model (`distilbert-base-uncased`) on the [Yelp Polarity dataset](https://huggingface.co/datasets/yelp_polarity). Two models are trained and compared to analyze how unfreezing part of the transformer affects performance, confidence, and generalization.

---

## 🔍 Project Summary

I compared two fine-tuning strategies:

1. **Model 1 — Classifier Only**: Only the final classification layer was trained.
2. **Model 2 — Last Encoder Layer Unfrozen**: The final classification layer and the last encoder layer were fine-tuned.

Both models were evaluated using accuracy, F1 score, and prediction confidence.

---

## 📊 Key Results

| Metric     | Model 1 (Classifier Only) | Model 2 (+Last Encoder Layer) |
|------------|----------------------------|-------------------------------|
| Accuracy   | 0.87                       | **0.92**                      |
| F1 Score   | 0.86                       | **0.92**                      |
| Agreement  | 453/500 test samples (90.6%) |                               |

✅ Model 2 achieved higher accuracy and F1 score, while showing stronger confidence and better generalization across the test set.


- **Python 3.10**
- [🤗 Hugging Face Transformers](https://github.com/huggingface/transformers)
- **PyTorch**
- **Hugging Face Datasets**
- **Scikit-learn**
- **Matplotlib / IPython** (for plots and display)
