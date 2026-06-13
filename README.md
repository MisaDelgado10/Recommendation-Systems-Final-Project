# Amazon Product Recommendation System

## Overview

This project develops and evaluates multiple recommendation algorithms for Amazon product recommendations using collaborative filtering and matrix factorization techniques.

The project was completed as part of a Machine Learning / Recommendation Systems final project under the **Kaggle Benchmark Deep Dive Track**.

The study investigates:

- Rank-Based Recommendation
- User-User Collaborative Filtering
- Item-Item Collaborative Filtering
- Matrix Factorization (SVD)
- Hyperparameter Optimization
- Hybrid Recommendation Models
- Failure Analysis

---

## Dataset

Amazon Product Recommendation ([Dataset](https://drive.google.com/file/d/1XahZcR287ke7j48I7-oj0KzmmwSSvA3Y/view?usp=sharing))

The dataset contains:

- User IDs
- Product IDs
- Ratings

The objective is to predict user preferences and recommend products that users have not previously interacted with.

---

## Project Structure

```text
├── main.ipynb
├── README.md
├── requirements.txt
└── figures/
```

---

## Models Implemented

### Baseline Models

1. Rank-Based Recommendation
2. User-User Collaborative Filtering
3. Item-Item Collaborative Filtering
4. Singular Value Decomposition (SVD)

### Tuned Models

1. Tuned User-User CF
2. Tuned Item-Item CF
3. Tuned SVD

### Proposed Models

#### Hybrid V1

Hybrid Score:

Hybrid Score = α × SVD + (1−α) × Popularity

#### Hybrid V2

Hybrid Score = α × SVD + (1−α) × (Average Rating + Rating Count)

---

## Evaluation Metrics

The following metrics were used:

- RMSE
- Precision@10
- Recall@10
- F1-score

---

## Final Results

| Model | RMSE | Precision@10 | Recall@10 | F1@10 |
|---------|---------|---------|---------|---------|
| User-User CF | 1.0012 | 0.855 | 0.858 | 0.856 |
| User-User CF Tuned | 0.9526 | 0.847 | 0.894 | 0.870 |
| Item-Item CF | 0.9950 | 0.838 | 0.845 | 0.841 |
| Item-Item CF Tuned | 0.9578 | 0.839 | 0.880 | 0.859 |
| SVD | 0.8882 | 0.853 | 0.880 | 0.866 |
| SVD Tuned | 0.8808 | 0.854 | 0.878 | 0.866 |
| Hybrid V1 (α=0.5) | - | 0.878 | 0.843 | 0.860 |
| Hybrid V2 (α=0.9) | - | 0.861 | 0.812 | 0.835 |

---

## Key Findings

- Tuned SVD achieved the lowest RMSE.
- Tuned User-User CF achieved the highest F1-score.
- Hybrid V1 achieved the highest Precision@10.
- Popularity-based enhancements improved precision but reduced recall.
- Cold-start users and sparse products remain major challenges.

---

## Reproducibility

### Hardware

- Apple MacBook M4
- 16 GB RAM

### Software

- Python 3.9
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn
- Surprise

---

## Running the Project

Note: Sometimes, the installation of the surprise library, which is used to build recommendation systems, faces issues in Jupyter. To avoid any issues, it is advised to use Google Colab for this project. For Google Colab just install this way: !pip install surprise

Install dependencies:

```bash
pip install -r requirements.txt
```

Run:

```bash
jupyter notebook main.ipynb
```

Execute all cells sequentially.

---

## Future Work

Potential future improvements include:

- Neural Collaborative Filtering
- Graph Neural Networks
- Temporal Recommendation Systems
- Content-Based Hybrid Models
- Transformer-based Recommenders