# **📘 README.md — Amazon Reviews: Sentiment Analysis \+ Clustering \+ Streamlit App**

## **🧠 Project Overview**

This project combines **Natural Language Processing (NLP)**, **Machine Learning**, and **Large Language Models (LLMs)** to analyze thousands of Amazon product reviews.

It includes two complete pipelines:

1. **Sentiment Classification** using a fine‑tuned Transformer model  
2. **Clustering \+ Embeddings \+ Topic Summaries** using KMeans and LLM‑generated summaries

A **Streamlit application** ties everything together, allowing users to:

* Classify text in real time  
* Assign reviews to clusters  
* Explore cluster summaries  
* Visualize embeddings  
* Inspect real examples from each cluster

The goal is to provide a full end‑to‑end review analysis system suitable for portfolio, GitHub, and Hugging Face deployment.

# **🗂️ Repository Structure**

Code  
Amazon\_Ironhack/  
│  
├── classification\_model/  
│   ├── model/  
│   │   ├── config.json  
│   │   ├── pytorch\_model.bin  
│   │   ├── tokenizer.json  
│   │   ├── tokenizer\_config.json  
│   │   └── special\_tokens\_map.json  
│   ├── outputs/  
│   │   ├── metrics.json  
│   │   └── training\_logs/  
│   └── README\_classification.md  
│  
├── clustering\_pipeline/  
│   ├── data\_raw/  
│   │   └── amazon\_reviews\_original.csv  
│   ├── data\_clean/          ← optional (may be empty)  
│   ├── embeddings/  
│   │   ├── embeddings.npy  
│   │   ├── reduced\_embeddings.npy  
│   │   ├── cluster\_labels\_kmeans.npy  
│   │   └── cluster\_labels\_hdbscan.npy  
│   ├── models/  
│   │   └── kmeans.pkl  
│   ├── clusters\_for\_summarization/  
│   │   ├── cluster\_summary.json  
│   │   ├── cluster\_summary\_kmeans.json  
│   │   ├── cluster\_0.txt  
│   │   ├── cluster\_1.txt  
│   │   ├── cluster\_2.txt  
│   │   ├── cluster\_3.txt  
│   │   ├── cluster\_4.txt  
│   │   └── cluster\_-1.txt  
│   ├── notebooks/  
│   │   └── Step02\_Embedding\_Clustering.ipynb  
│   └── README\_clustering.md  
│  
├── streamlit\_app/  
│   ├── app.py  
│   ├── utils.py  
│   ├── requirements.txt  
│   ├── components/  
│   └── assets/  
│  
├── .gitignore  
└── README.md   ← this file

# **🔍 1\. Sentiment Classification Pipeline**

### **✔ Model**

A Transformer model fine‑tuned on Amazon reviews (BERT / DistilBERT / RoBERTa depending on training).

### **✔ Key Files**

* `pytorch_model.bin` — model weights  
* `config.json` — architecture  
* `tokenizer.json` — tokenizer  
* `outputs/` — training metrics and logs

### **✔ Features**

* Real‑time sentiment prediction  
* Evaluation metrics  
* Integration with Streamlit

# **🔍 2\. Clustering Pipeline**

### **✔ Embeddings**

Generated using a Transformer model (sentence embeddings).

Files:

* `embeddings.npy`  
* `reduced_embeddings.npy` (PCA/UMAP for visualization)

### **✔ Clustering**

* KMeans with 5 clusters  
* HDBSCAN optional

Model file:

* `models/kmeans.pkl`

### **✔ Summaries**

Generated using an LLM based on the text inside each cluster.

Files:

* `cluster_summary.json`  
* `cluster_summary_kmeans.json`  
* `cluster_*.txt`

# **🎨 3\. Streamlit Application**

The Streamlit app provides an interactive interface to explore the entire project.

### **✔ Features**

* Real‑time sentiment classification  
* Cluster assignment for new text  
* Cluster summaries  
* 2D embedding visualization  
* Real examples per cluster

### **✔ Run locally**

bash  
cd streamlit\_app  
streamlit run app.py

# **📦 Installation**

### **1\. Clone the repository**

bash  
git clone https://github.com/\<your-username\>/amazon-reviews-sentiment-clustering.git  
cd amazon-reviews-sentiment-clustering

### **2\. Install dependencies**

bash  
pip install \-r streamlit\_app/requirements.txt

# **🚀 Deploy on Hugging Face Spaces**

1. Create a new Space  
2. Select **Streamlit**  
3. Upload the `streamlit_app/` folder  
4. Add your models as assets or load them from Hugging Face Hub  
5. Run the app

# **📊 Results**

* Fine‑tuned sentiment classifier with stored metrics  
* 5 meaningful clusters extracted from embeddings  
* LLM‑generated summaries for each cluster  
* Interactive visualization and exploration via Streamlit