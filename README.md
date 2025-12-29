# Sentiment and Semantic Analysis of Azerbaijani YouTube Comments

This repository contains an end-to-end pipeline for **sentiment and semantic analysis of Azerbaijani-language YouTube comments**, developed as part of the **Advanced AI course (SABAH groups)** at **Azerbaijan State Oil and Industrial University**.

The project focuses on low-resource language challenges and explores how **textual content, emojis, confidence thresholds, and semantic structure** interact in sentiment analysis.

Colab link: https://colab.research.google.com/drive/1zHDvrQ0koQQD_smZpbQEdu96OaSINqnv?usp=sharing
---

## Project Objectives

- Collect and preprocess Azerbaijani YouTube comments
- Normalize informal and noisy social media text
- Perform sentiment analysis using transformer-based models
- Analyze the effect of **confidence thresholds (0.6, 0.8)**
- Study the impact of **comment length filtering**
- Investigate **emoji–text sentiment inconsistency**
- Perform **semantic similarity and outlier analysis**
- Classify comments into **semantic categories** and analyze sentiment distribution per category

---

## Dataset

Each comment includes the following fields:

- `comment_text` — raw comment text
- `text_no_url` — text with URLs removed
- `text_no_emoji` — clean text without emojis
- `emojis` — extracted emojis
- `emoji_text` — wordified emojis (e.g., `crying_face`)
- `like_count` — number of likes
- `reply_count` — number of replies

At least **1000 comments** were collected from an Azerbaijani-language YouTube video.

---

## Models Used

### Text Sentiment
- **LocalDoc/sentiment_analysis_azerbaijani**  
  (3-class: positive / neutral / negative)

### Emoji Sentiment
- **cardiffnlp/twitter-xlm-roberta-base-sentiment**  
  (multilingual, emoji-aware)

### Semantic Similarity
- **paraphrase-multilingual-MiniLM-L12-v2**

### Semantic Categorization
- **XLM-R large (XNLI)** using zero-shot classification

---

## Experiments & Analyses

### 1. Confidence Threshold Analysis
- Thresholds: **0.6** and **0.8**
- Compared sentiment distributions and uncertainty behavior

### 2. Comment Length Filtering
- Minimum word counts: **≥3, ≥5, ≥7**
- Analyzed sentiment stability across thresholds

### 3. Analytical Tasks
- Emoji–Text sentiment inconsistency
- Semantic similarity groups (cosine similarity)
- Semantic outliers (bottom 5%)
- Popular comment analysis using likes and replies

### 4. Semantic Category-Based Sentiment
Comments classified into:
1. Rational positive feedback
2. Emotional reaction
3. Criticism and dissatisfaction
4. Direct address to the author
5. Troll / non-constructive comment

Sentiment distribution analyzed per category.

---

## Key Findings

- Language-specific models significantly outperform generic multilingual baselines for Azerbaijani
- Emojis often convey emotional signals that contradict textual sentiment
- Longer comments exhibit more stable sentiment across confidence thresholds
- Semantic categories show distinct sentiment profiles
- Overconfidence is a notable characteristic of Azerbaijani-specific sentiment models

---

## Notes & Limitations

- Azerbaijani is a low-resource language; available sentiment models are limited
- Some emotionally complex expressions (e.g., condolences) challenge standard sentiment definitions
- Results emphasize analysis and interpretation rather than model fine-tuning

