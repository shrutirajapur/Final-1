Project Title
AI-Powered Customer Support Intelligence Platform
Skills take away From This Project

Natural Language Processing (NLP) — Text Classification, Sentiment Analysis, Named Entity Recognition


Transformer Fine-tuning (DistilBERT / BERT) on real-world support text


Exploratory Data Analysis (EDA) and Data Visualization


Text Preprocessing (tokenization, stopword removal, lemmatization, TF-IDF)


Data Preprocessing (handling missing values, encoding categorical variables, feature scaling)


Classical ML Classification Algorithms (Logistic Regression, Decision Trees, Random Forest, XGBoost, LightGBM)


Deep Learning — MLP for tabular data, LSTM/BiLSTM for sequential text


Multi-task Learning (simultaneous classification and regression targets)


Unsupervised Learning — Customer Segmentation via K-Means Clustering


Model Evaluation (Accuracy, F1-Score, ROC-AUC, BLEU, Cosine Similarity)


Experiment Tracking with MLflow


Hyperparameter Tuning with Optuna / GridSearchCV


Model Explainability with SHAP
End-to-End ML Pipeline (scikit-learn Pipelines + HuggingFace Transformers)


Model Deployment using FastAPI + Docker (deployed to Hugging Face Spaces / Render)


Dashboard creation using Power BI / Plotly Dash


Git version control and production-grade project structuring
Domain
SaaS / E-Commerce / Customer Experience (CX) / AI Operations


Problem Statement:
The volume of customer support tickets across SaaS, e-commerce, and technology companies has grown exponentially. Manual ticket routing, prioritization, and resolution are slow, inconsistent, and expensive. This project tasks students with building an AI-powered end-to-end Customer Support Intelligence Platform that automates three interconnected tasks using the Customer Support Ticket Dataset from Kaggle:
Ticket Type Classification (NLP) — Automatically classify incoming tickets into categories (Billing / Technical / Account / Product Inquiry) using the free-text Ticket Subject and Ticket Description fields. Core NLP task using DistilBERT fine-tuning.
Ticket Priority Prediction (Tabular ML) — Predict the urgency level (Low / Medium / High / Critical) of a ticket using structured features (channel, product, customer age, etc.).
Resolution Time Estimation (Regression) — Estimate how many hours a ticket will take to resolve using a combination of text and tabular features.

Students must build a production-grade system — not just a notebook — encompassing text preprocessing, transformer fine-tuning, tabular ML pipelines, experiment tracking, model explainability, unsupervised customer segmentation, and a deployed FastAPI inference endpoint.
Business Use Cases:
Intelligent Ticket Routing: Automatically route incoming tickets to the correct department without manual triage, reducing average handling time.
SLA Compliance: Predict resolution time upfront so that high-priority tickets can be escalated before SLA breaches occur.
Agent Workload Balancing: Forecast ticket volumes by type and priority to allocate agents efficiently across shifts.
Customer Retention: Identify patterns in low satisfaction ratings (CSAT) and proactively flag at-risk customers for intervention.
Self-Service Deflection: Identify the most common ticket types to build targeted FAQ and chatbot responses, reducing ticket volume.
GenAI Extension (Optional): Use the Resolution column to fine-tune a generative model or prompt an LLM to auto-draft replies for classified ticket types.


Approach:
EDA & Data Understanding: Analyse distributions of Ticket Type, Priority, Channel, and Satisfaction Rating. Visualise text length distributions, word clouds, and class imbalance using Matplotlib, Seaborn, and Plotly.
Build an interactive EDA Dashboard using Plotly Dash or Power BI covering ticket volume trends, satisfaction heatmaps, and channel performance.
Text Preprocessing Pipeline:
Lowercase, remove punctuation and HTML artifacts.
Tokenize, remove stopwords, apply lemmatization (spaCy / NLTK).
Compute TF-IDF vectors for baseline models.
Generate sentence embeddings using pre-trained BERT tokenizer for transformer models.
Tabular Feature Engineering: Encode Ticket Channel, Product Purchased, Customer Gender. Extract ticket age (days since purchase). Compute character count and word count of description as numeric features.
Split data into train / validation / test sets using stratified splitting to preserve class proportions.
Baseline Models: Train Logistic Regression and Naive Bayes (Multinomial) on TF-IDF features. Record baseline Accuracy, F1-macro, and ROC-AUC.
Advanced Classical ML: Train Random Forest, XGBoost, LightGBM on combined tabular + TF-IDF features. Use cross-validation for robust estimation.
Deep Learning — BiLSTM: Build a Keras/PyTorch BiLSTM with GloVe embeddings (100d) on the Ticket Description text. Apply BatchNorm and Dropout. Compare against classical models.
Transformer Fine-tuning (DistilBERT): Fine-tune a pre-trained DistilBERT model using Hugging Face Transformers on the combined Ticket Subject + Ticket Description text for multi-class Ticket Type classification. Use AdamW optimizer with learning rate warmup.
Regression Sub-task: Train XGBoost / LightGBM regressor on tabular + text features to predict Time to Resolution. Evaluate with RMSE, MAE, and R².
Unsupervised Segmentation: Apply K-Means clustering on customer profile features. Visualise clusters with PCA / t-SNE. Derive business-meaningful segment labels.
Experiment Tracking with MLflow: Log all model runs (parameters, metrics, artifacts). Use MLflow Model Registry to version the production model.
Hyperparameter Tuning: Use Optuna for XGBoost/LightGBM and Hugging Face Trainer hyperparameter search for DistilBERT.
Explainability (SHAP): Generate SHAP summary, waterfall, and dependence plots for best tabular model. Provide token-level attention visualisation for DistilBERT predictions.
Deployment — FastAPI + Docker: Wrap the best pipeline (DistilBERT ticket classifier + tabular priority predictor) in a FastAPI app. Containerise with Docker. Deploy to Hugging Face Spaces or Render. Submit the live public URL.


Results: 
A fine-tuned DistilBERT model that classifies ticket types from raw customer text with high F1-macro score.
A trained XGBoost / LightGBM pipeline for ticket priority prediction and resolution time estimation.
Customer segmentation report with cluster profiles and business interpretations.
MLflow experiment dashboard with all model runs logged and compared.
SHAP explainability report for the best tabular model.
Deployed FastAPI inference endpoint — public URL submitted with the project.
Interactive Power BI / Plotly Dash dashboard: ticket volume by type, CSAT trends, resolution time by channel, model performance KPIs.
Well-structured GitHub repository with README, requirements.txt, Dockerfile, and final project report.
Project Evaluation metrics:
NLP Classification (Ticket Type / Priority): F1-Score (macro and weighted), Accuracy, ROC-AUC, Confusion Matrix
Regression (Time to Resolution): RMSE, MAE, R²
Unsupervised (Clustering): Silhouette Score, Davies-Bouldin Index, cluster interpretability
Deployment: API response latency < 500ms per prediction, Docker build success, live endpoint verification
MLflow: Minimum 10 logged experiment runs with measurable improvement over baselin
Technical Tags:
Python | Pandas | NumPy | Scikit-learn | NLTK | spaCy | TF-IDF | GloVe | Hugging Face Transformers | DistilBERT | BERT | PyTorch | Keras | BiLSTM | XGBoost | LightGBM | Random Forest | MLflow | Optuna | SHAP | FastAPI | Docker | K-Means | PCA | t-SNE | Plotly | Power BI | Seaborn | Matplotlib | Git | Joblib
Data Set:
Source - https://drive.google.com/file/d/1Xr-7TlAunE4uYI07sxhTOXiIcs0wZboz/view?usp=sharing

Data Set Explanation:
Primary NLP Target — Ticket Type (Multi-class: Billing / Technical / Account / Product Inquiry)
Secondary Target — Ticket Priority (Multi-class: Low / Medium / High / Critical)
Regression Target — Time to Resolution (continuous, in hours)

Variable
Description
Ticket ID
Unique identifier for each support ticket
Customer Name
Name of the customer who raised the ticket
Customer Email
Email address of the customer
Customer Age
Age of the customer in years
Customer Gender
Gender of the customer (Male / Female / Other)
Product Purchased
Name of the product/service the ticket is related to
Date of Purchase
Date when the product/service was purchased
Ticket Type
Category of the issue — Billing / Technical / Account / Product Inquiry (PRIMARY TARGET for NLP classification)
Ticket Subject
Short summary line of the ticket written by the customer (text feature for NLP)
Ticket Description
Full free-text description of the customer's issue (primary NLP input column)
Ticket Status
Current status of the ticket — Open / Pending Customer Response / Closed
Resolution
Agent's free-text resolution response (used for generative modelling / response quality NLP)
Ticket Priority
Priority assigned to the ticket — Low / Medium / High / Critical (SECONDARY TARGET for classification)
Ticket Channel
Channel through which the ticket was raised — Email / Chat / Social Media / Phone
First Response Time
Time taken for the first agent response (hours) — used as regression target
Time to Resolution
Total time taken to resolve the ticket (hours) — PRIMARY regression target
Customer Satisfaction Rating
Post-resolution satisfaction score given by the customer (1–5 scale) — TERTIARY TARGET

