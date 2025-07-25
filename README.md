# Misinfo 79K-NLP Project
NLP pipeline for measuring misinformation (MISI) on a 79k “fake vs. true” news dataset.
## Project Overviews
### Data Sources
- Fake News Dataset: DataSet_Misinfo_FAKE.csv
- True News Dataset: DataSet_Misinfo_TRUE.csv
### Tools
- Python 3.x: Core scripting language for data processing, modeling, and analysis.
- Jupyter Notebooks / Google Colab: Interactive prototyping (data cleaning, embedding, network construction, visualization).
- pandas & NumPy: DataFrame and array structures plus vectorized operations for handling the 79k–row corpus.
- USM & BERT embeddings:
1) USM (Unsupervised Semantic Model) for extracting raw topics/entities from text
2) BERT (via Hugging Face Transformers) to convert sentences/paragraphs into contextual embedding vectors.
- networkx: Builds the topic–entity co-occurrence graph (nodes = topics/entities; edge weights = co-occurrence counts).
- python-louvain (community): Applies the Louvain algorithm on our graph to detect “consensus” clusters—used in the consensus-weight step of MISI.
- tqdm: Lightweight progress bars around loops (e.g., embedding batches, graph-construction loops).
- scikit-learn & statsmodels:
1) scikit-learn for train/test splits and auxiliary ML tasks
2) statsmodels for OLS regressions when validating MISI against drivers (topic/entity frequency) and outcomes.
- Matplotlib & Seaborn: Publication-quality figures - bar charts of average MISI by topic, event-window plots, regression diagnostics, etc.
### Steps
### 1. Topic-Entity Labelling: 
- File: Misinformation_&_Fake_News_text_dataset_79k.ipynb
- Explanation: It loads the 79k “fake vs. true” news dataset, cleans and normalizes the text, computes basic text‐length features, splits into train/validation/test sets, and exports the results as CSVs.
### 2. Embedding
- File: Misinfo_79k_Embedding.ipynb
- Explanation: It loads the cleaned 79k–article dataset, initializes a BERT tokenizer and model, batches the text through BERT (with tqdm progress bars) to compute contextual embedding vectors, and then saves those embeddings (e.g. as a CSV) for downstream MISI network and analysis. 
### 3. Network & MISI
- File: Misinfo 79k-Reliability-Weighted Network & MISI.ipynb
- Explanation: It loads the BERT embeddings, builds a reliability-weighted topic–entity co-occurrence graph with consensus clustering, computes each document’s MISI score, and exports the results.
### 4. Drivers & Consequences
- File: Drivers_&_Concequences.ipynb
- Explanation: It merges the MISI scores with driver and outcome variables, runs OLS regressions to identify what drives misinformation and its consequences, and outputs the regression tables and diagnostic plots.
