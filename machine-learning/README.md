# 🧠 Machine Learning Layer

This folder contains the machine learning and decisioning layer used by the **AI Voice Sales & Lead Prioritization System**.

## What the model does

The pipeline predicts whether a customer is likely to return within **30 days**, then turns the prediction into actionable business decisions for marketing and outbound AI calling.

### End-to-end flow

```text
Historical Customer Orders
        ↓
Data Cleaning
        ↓
Order-Level Feature Engineering
        ↓
Customer History Features
        ↓
30-Day Return Prediction
        ↓
Customer Risk / Return Segmentation
        ↓
Marketing & Package Recommendation
        ↓
Lead Scoring
        ↓
Call Priority Ranking
        ↓
Dynamic Voice AI Call Brief
        ↓
Retell AI Outbound Calling
```

## Model

**Algorithm:** Random Forest Classifier  
**Validation:** Time-based holdout

### Validation performance

- Accuracy: **81.7%**
- ROC-AUC: **0.881**
- Precision: **0.847**
- Recall: **0.887**
- F1 Score: **0.867**

The time-based validation approach was used to better approximate future production behavior rather than relying on a random train/test split.

## Decision Layers

The notebook includes more than prediction alone:

- Customer return probability
- Risk segmentation
- Customer value segmentation
- Frequency segmentation
- Inactivity segmentation
- Marketing incentive behavior
- Package recommendation logic
- Call/no-call decisioning
- Call objective generation
- Lead priority scoring
- Queue ranking
- Dynamic call briefs for the AI voice agent

## Files

```text
machine-learning/
├── README.md
├── customer-return-prediction-and-lead-prioritization.ipynb
└── requirements.txt
```

## Data

The production dataset is **not included** because it contains private customer and business information.

To run the notebook with your own compatible dataset, set:

```bash
CUSTOMER_DATA_PATH=data/customer_orders_sample.xlsx
```

or update the `DATA_PATH` value in the first data-loading section.

## Privacy

The portfolio notebook has been sanitized:

- customer-level outputs removed
- phone numbers and IDs removed from notebook outputs
- production dataset excluded
- company-specific names anonymized
- temporary/debug cells removed
- Google Colab-only download logic removed
