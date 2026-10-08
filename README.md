# Segmora


> Customer Segmentation and Segment-Specific Product Association Analysis for Online Retail

Segmora is an unsupervised machine-learning group project developed for the **IT3091 Machine Learning** module at Sri Lanka Institute of Information Technology (SLIIT).

The project analyses the UCI Online Retail dataset to help an online retailer understand customer purchasing behaviour, identify meaningful customer segments, and generate targeted product-bundling recommendations.

---

## Business Problem

An online retailer wants to improve sales, customer retention, and product strategy using historical transaction data.

The dataset contains transactional purchase records but does not provide predefined customer labels. Therefore, the project uses unsupervised learning to discover meaningful groups of customers based on their purchasing behaviour.

---

## Project Objectives

### Primary Lens: Customer Segmentation

Identify interpretable and actionable customer segments using:

- Classical RFM features: Recency, Frequency, and Monetary value
- Domain-augmented behavioural features
- Unsupervised clustering algorithms
- Cluster quality, stability, interpretability, and business usefulness

### Secondary Lens: Product Association and Bundling

Perform market-basket analysis within the identified customer segments to discover targeted product associations and bundling opportunities.

This segment-specific approach is preferred over generic association rules because different customer groups may purchase different product combinations.

---

## Dataset

| Item | Details |
|---|---|
| Dataset | UCI Online Retail |
| Source | UCI Machine Learning Repository |
| Link | https://archive.ics.uci.edu/dataset/352/online+retail |
| Raw dataset file | `Online Retail.xlsx` |
| Data period | 1 December 2010 to 9 December 2011 |
| Raw data granularity | Invoice-line transaction |
| Customer-segmentation unit | Customer |
| Market-basket unit | Invoice / shopping basket |

### Raw Variables

- `InvoiceNo` — Invoice identifier; values beginning with `C` indicate cancellation invoices
- `StockCode` — Product identifier
- `Description` — Product description
- `Quantity` — Number of purchased or returned units
- `InvoiceDate` — Invoice date and time
- `UnitPrice` — Price per unit
- `CustomerID` — Customer identifier
- `Country` — Customer country

> The raw dataset is stored privately in the group Google Drive and is not committed to this repository.

---

## Analytical Workflow

```text
Business Problem Framing
        ↓
Data Understanding and Exploratory Data Analysis
        ↓
Data Cleaning and Preprocessing
        ↓
Customer-Level Feature Engineering
        ↓
Unsupervised Clustering Model Comparison
        ↓
Cluster Evaluation and Stability Analysis
        ↓
Segment-Specific Apriori Association Rules
        ↓
Business Recommendations and Limitations
```

---

## Customer-Level Features

After transaction cleaning and aggregation, the project will construct customer-level features including:

| Feature | Meaning |
|---|---|
| Recency | Days since the customer's most recent completed purchase |
| Frequency | Number of completed invoices per customer |
| Monetary | Total completed-purchase revenue per customer |
| Return rate | Customer cancellation/return behaviour using a documented formula |
| Item diversity | Number of unique products purchased |
| Average basket value | Average revenue per completed invoice |
| Average basket size | Average number of products per invoice |
| Total quantity | Total positive quantity purchased |

---

## Models and Methods

### Clustering Methods

The project will compare the following unsupervised learning methods:

- K-Means clustering
- Agglomerative hierarchical clustering
- DBSCAN
- Gaussian Mixture Models (GMM)

### Association-Rule Mining

- Apriori algorithm
- Support
- Confidence
- Lift
- Segment-specific rule interpretation and business relevance

### Evaluation

The final segmentation will be assessed using:

- Silhouette Score
- Calinski-Harabasz Score
- Davies-Bouldin Score
- Stability across repeated runs and resampling
- Cluster size balance
- Interpretability and business actionability
- PCA-based cluster visualisation

---

## Repository Structure

```text
segmora/
│
├── notebooks/
│   └── Segmora_2026_AI_40.ipynb
│
├── outputs/
│   ├── figures/
│   └── tables/
│
├── docs/
│   ├── decision_log.md
│   ├── data_dictionary.md
│   ├── eda_insight_log.md
│   └── team_contributions.md
│
├── data/
│   └── README.md
│
├── README.md
├── .gitignore
└── requirements.txt
```

---

## Team Responsibilities

| Member | Responsibility |
|---|---|
| Ranawansha P. G. D. D. | Project setup, business framing, data understanding, EDA, data-quality audit, and preprocessing handover |
| Vimukthi L. H. T. P. | Data cleaning, preprocessing pipeline, RFM, and behavioural feature engineering |
| Sandul T. H. N. N. | K-Means tuning, alternative clustering models, and segment-specific market-basket analysis |
| Gamage K. T. P. | Cluster evaluation, stability analysis, PCA visualisation, business recommendations, limitations, and final integration |

---

## Collaboration Protocol

This repository uses one sequential end-to-end notebook.

1. Each member downloads the latest notebook from GitHub before beginning their stage.
2. Only one member edits the notebook at a time.
3. The member runs the full notebook in Google Colab before uploading.
4. The updated notebook replaces the previous notebook version in GitHub.
5. Each update includes a meaningful commit message showing the completed stage.
6. The next member begins only after the current member confirms that the latest version has been uploaded.

### Commit Message Format

```text
stage: concise description of completed work
```

Examples:

```text
eda: add raw feature distributions and data-quality audit
preprocess: clean completed-purchase transactions and remove invalid records
features: create RFM and augmented behavioural features
model: tune K-Means and compare clustering methods
association: mine segment-specific Apriori rules
evaluation: add metrics, PCA visualisation, and recommendations
```

---

## Reproducibility

- Environment: Google Colab
- Primary language: Python
- Random seed: `42`
- Raw dataset source and path are documented in the notebook
- Key data-cleaning, preprocessing, modelling, and evaluation decisions will be recorded in the decision log
- The final notebook will run end-to-end and reproduce all reported tables and figures

---

## Academic Use and Attribution

This repository is created solely for the IT3091 Machine Learning group assignment at SLIIT.

Dataset citation:

> Online Retail [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33

The project uses GitHub for version history, collaboration, reproducibility, and transparent documentation of the group’s analytical workflow.
