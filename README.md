# SMS Spam Classifier

A text classification project that detects spam SMS messages, comparing six
machine learning models on the UCI SMS Spam Collection dataset.

**Tech:** Python, pandas, NLTK, scikit-learn, XGBoost, seaborn

---

## The problem

Spam texts range from annoying to outright fraudulent. The goal was to build a
classifier that separates spam from legitimate messages ("ham"), and to find out
which kind of model handles short, informal text best.

## Data

- **Dataset:** UCI SMS Spam Collection, 5,572 labelled English text messages
- **Cleaning:** removed 403 duplicate messages, leaving **5,169**
- **Class balance:** heavily imbalanced, with only about 14% spam

That imbalance matters. A model that labelled every message "ham" would still
score around 86% accuracy, so accuracy alone is a misleading measure here. The
results below focus on how well each model catches spam.

## Approach

1. **Preprocessing:** removed URLs, mentions and hashtags, dropped English
   stopwords, and lemmatised words with NLTK
2. **Vectorisation:** bag-of-words with scikit-learn's `CountVectorizer`,
   fitted on the training set only
3. **Split:** 80% train, 20% test (1,034 test messages, 145 of them spam)
4. **Models compared:** Logistic Regression, Bernoulli Naive Bayes, Random
   Forest, AdaBoost, Gradient Boosting and XGBoost

## Results (test set)

| Model | Accuracy | Spam precision | Spam recall | Spam F1 |
|---|---|---|---|---|
| **Logistic Regression** | **97.9%** | 0.99 | 0.86 | **0.92** |
| AdaBoost | 97.6% | 0.97 | 0.86 | 0.91 |
| XGBoost | 97.4% | 0.93 | **0.88** | 0.90 |
| Bernoulli Naive Bayes | 97.2% | **1.00** | 0.80 | 0.89 |
| Random Forest | 97.2% | 0.99 | 0.81 | 0.89 |
| Gradient Boosting | 97.0% | 0.98 | 0.80 | 0.88 |

## What the results show

- **Logistic Regression gave the best overall balance** (highest F1), wrongly
  flagging just 1 legitimate message out of 889 while catching 124 of 145 spam
  messages.
- **There's a real precision vs recall trade-off.** Naive Bayes never flagged a
  legitimate message, but missed one in five spam texts. XGBoost caught the
  most spam, at the cost of more false alarms.
- **Which model is "best" depends on the use case.** For a phone's spam filter,
  hiding a real message is worse than letting some spam through, which favours
  high precision. For fraud screening, catching more spam would matter more.
- **Simple models held their own.** A linear model on word counts matched or
  beat the ensemble methods, which is common for short text.

## Limitations and next steps

- Logistic Regression and Random Forest reached 100% training accuracy, a sign
  of some overfitting worth addressing with regularisation and cross-validation.
- Accuracy-based model selection could be replaced with F1 or precision-recall
  curves, given the class imbalance.
- TF-IDF features, threshold tuning or a small transformer model would be
  natural next experiments.

## Run it

```bash
git clone https://github.com/NicholusMagak/SMS-Spam-Collection.git
cd SMS-Spam-Collection
pip install pandas nltk scikit-learn xgboost seaborn matplotlib
jupyter notebook Index.ipynb
```

The dataset is included in `archive/spam.csv`.
