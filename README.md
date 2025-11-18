# Multi-Modal Fake Review Detection System

![Status](https://img.shields.io/badge/Status-Completed-success)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Tech](https://img.shields.io/badge/Stack-PyTorch%20%7C%20PyG%20%7C%20XGBoost%20%7C%20S-BERT-orange)

> **The integrity of modern digital marketplaces is increasingly compromised by sophisticated review fraud.** This project implements a robust detection system leveraging textual semantics, behavioral profiling, and relational graph structures.

## 📌 Problem Statement
To detect deceptive review patterns and profile suspicious reviewer behavior on Google Maps by constructing a heterogeneous graph neural network. [cite_start]This system integrates textual semantics (BERT), behavioral metadata (XGBoost), and spatiotemporal anomalies into a unified, **unsupervised anomaly detection framework**[cite: 32].

## 🚀 Core Objectives
* [cite_start]**Textual Analysis:** Implement `all-MiniLM-L6-v2` (Sentence-BERT) to capture semantic nuances[cite: 35].
* [cite_start]**Behavioral Profiling:** Construct user/business profiles using **XGBoost** to aggregate temporal and rating patterns[cite: 36].
* [cite_start]**Graph Modeling:** Model complex relationships using **Relational Graph Neural Networks (RGCN)** to detect structural fraud[cite: 37].
* [cite_start]**Deep Fusion:** Integrate all three modalities to distinguish fake reviews without labeled training data[cite: 38].

## 🏗️ System Architecture
The project follows a multi-modal pipeline approach:

1.  [cite_start]**Data Ingestion:** Stratified sampling of 125,000 reviews from 8 US states (UCSD Google Maps Dataset) [cite: 49-55].
2.  **Feature Engineering:**
    * *NLP:* 384-dimensional text embeddings.
    * [cite_start]*Behavioral:* `user_rating_variance`, `review_hour`, `business_diversity` [cite: 66-69].
    * [cite_start]*Spatiotemporal:* **"Fast Travel"** logic to flag impossible movement between states[cite: 67].
3.  **Graph Construction:** A Heterogeneous Graph where Users and Businesses are nodes, and Reviews are edges carrying text embeddings.
4.  **Detection:** A Hybrid RGCN model trained via self-supervised link prediction and anomaly scoring.

## 📂 Dataset
* [cite_start]**Source:** [UCSD Large-Scale Social Data Lab](https://mcauleylab.ucsd.edu/public_datasets/gdrive/googlelocal/) [cite: 50]
* **Size:** 125,000 Reviews (100k Train / 25k Test)
* [cite_start]**Regions:** Kentucky, Hawaii, Minnesota, California, Texas, New York, Florida, Illinois[cite: 55].

## 🛠️ Installation & Usage

### 1. Prerequisites
This project requires Python 3.8+ and PyTorch.

```bash
git clone [https://github.com/smruthi-bs/AFML-Fake-Review-Detection.git](https://github.com/smruthi-bs/AFML-Fake-Review-Detection.git)
cd AFML-Fake-Review-Detection
pip install -r requirements.txt
```

### 2. Data Setup  
Due to size limits, the dataset is not hosted on GitHub.  

- Download the `AFML_data` folder from the Google Drive link present in `data/README.md`.  
- Place the files into the `data/` directory of this repository.  
- Ensure `train_embeddings.npy` and `hetero_graph.pt` are present.

### 3. Running the Pipeline

To train the unified model and run inference using Jupyter notebooks:

- Open the provided `.ipynb` notebook in your environment (e.g., Jupyter Notebook, Colab).
- Make sure the data setup from step 2 is completed (i.e., files are placed correctly).
- Run the cells sequentially to execute training and inference.

## Team Members

- Smruthi B S (PES1UG23AM308): Feature Engineering & Graph Construction 
- Sneha Verma (PES1UG23AM309): Baseline & Hybrid XGBoost Models 
- Thanushree C B (PES1UG23AM338): NLP Text Embeddings 
- Vidyashree M B (PES1UG23AM348): GNN Model Architecture

Submitted for Advanced Foundations for Machine Learning Course Project, November 2025.
