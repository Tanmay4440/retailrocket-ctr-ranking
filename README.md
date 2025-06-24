# 🛍️ Retailrocket CTR Prediction and Ranking (MAP@12)

This project builds a **Click-Through Rate (CTR) Prediction & Ranking system** using the [Retailrocket eCommerce dataset](https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset), modeling customer interaction behavior and evaluating results using **MAP@12**.

---

## 🧠 Objective

Given a customer's session behavior, rank the most relevant items they are likely to click. The goal is to maximize **user engagement** through **accurate offer ranking** using real e-commerce logs.

---

## 📦 Dataset Description

The dataset includes 3 main files:

| File Name            | Description                                 |
|----------------------|---------------------------------------------|
| `events.csv`         | All user interactions (clicks, add-to-cart) |
| `item_properties.csv`| Item metadata including prices and category |
| `category_tree.csv`  | Hierarchical mapping of item categories     |

Each row corresponds to a user's interaction at a specific timestamp.

---

## 🏗️ Project Highlights

- Connected multiple data files using `itemid` and `visitorid`
- Engineered session-based and item-level features
- Simulated 30-min sessions for session ranking
- Converted CTR task to a **ranking task per session**
- Trained multiple models and evaluated using **MAP@12**

---

## 🧪 Models Used

| Model      | Type    | MAP@12   |
|------------|---------|----------|
| LightGBM   | Ranker  | `0.64081` |
| XGBoost    | Ranker  | `0.64153` |
| CatBoost   | Ranker  | `0.65011` |

---

## 📈 Evaluation Metric

**MAP@12** (Mean Average Precision at K = 12)

MAP@K evaluates the ranking of clicked items per session. We calculate it using grouped `session_id`, predicted scores, and ground truth.

---

## 🚀 How to Run This Project

### ✅ Option 1: Google Colab

Just open the notebook in Colab, and run all cells.

### ✅ Option 2: Locally (Jupyter)

1. Clone the repo  
2. Install requirements  
```bash
pip install -r requirements.txt
