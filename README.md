# Misinfo 79K-NLP Project
NLP pipeline for measuring misinformation (MISI) on a 79k “fake vs. true” news dataset.
## Project Overviews
### Datasets
-DataSet_Misinfo_FAKE.csv
-DataSet_Misinfo_TRUE.csv
### Tools
-Python 3.x
Core scripting language for data processing, modeling, and analysis.
-Jupyter Notebooks / Google Colab
Interactive prototyping (data cleaning, embedding, network construction, visualization).

pandas & NumPy
DataFrame and array structures plus vectorized operations for handling the 79 k–row corpus.

USM & BERT embeddings
– USM (Unsupervised Semantic Model) for extracting raw topics/entities from text
– BERT (via Hugging Face Transformers) to convert sentences/paragraphs into contextual embedding vectors.

networkx
Builds the topic–entity co-occurrence graph (nodes = topics/entities; edge weights = co-occurrence counts).

python-louvain (community)
Applies the Louvain algorithm on our graph to detect “consensus” clusters—used in the consensus-weight step of MISI.

tqdm
Lightweight progress bars around loops (e.g. embedding batches, graph-construction loops).

scikit-learn & statsmodels
– scikit-learn for train/test splits and auxiliary ML tasks
– statsmodels for OLS regressions when validating MISI against drivers (topic/entity frequency) and outcomes.

Matplotlib & Seaborn
Publication-quality figures: bar charts of average MISI by topic, event-window plots, regression diagnostics, etc.
### ETL Pipelines & Trend Analysis
- RLS162Demo ETL with trend analysis.ipynb
- Sepidar01_ETL.ipynb
### Power BI Dashboards
- RLS162Demo.pbix
- Sepidar01.pbix
### Machine Learning Notebooks
- Regression model for house prices.ipynb
- Predicting On-Time Delivery (Intermediate).ipynb
