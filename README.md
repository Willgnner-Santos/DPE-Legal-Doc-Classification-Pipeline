# Evaluation of Large Language Models for Classifying Legal Documents in Portuguese

This project evaluates the application of Large Language Models (LLMs) in the classification of legal documents, focusing on the Public Defender's Office of the State of Goiás (DPE-GO). Using a Brazilian legal corpus, advanced LLMs were assessed. Various text processing methods were employed to evaluate the models' effectiveness. The results show that LLMs, particularly the Llama-3.1-70B-Instruct-Turbo, achieve accuracy rates of up to **99.92%**.

We conclude that integrating LLMs can significantly enhance efficiency and standardization in the analysis of legal texts, providing effective support to public defenders. The repository includes four types of developed methods: summaries, descriptions, direct classification, and the use of centroids. Other LLMs were used, with the main differences being in model loading and the configuration of the context length supported by the selected LLM.

## Prerequisites

- **Python 3.8+**
- **Google Colab** (or local environment with Jupyter Notebook)
- **API Key** to access the model 

## Installation

Install necessary dependencies:

```bash
pip install tiktoken langchain-community langchainhub langchain_openai langchain pandas matplotlib scikit-learn seaborn
pip install imbalanced-learn
```

1. Mount Google Drive:
   - The project required access to Google Drive to load the corpus and save the results.
   - Run the following command in Colab:
     
```bash
from google.colab import drive
drive.mount('/content/drive')
```

2. Model Configuration:
  - Configure ChatOpenAI with your desired API key and template. The LLMs available from the [Together.AI](https://docs.together.ai/docs/chat-models).

**Llama-3.1-70B-Instruct-Turbo**

```bash

from langchain_openai import ChatOpenAI

api_key = 'YOUR_API_KEY'
llm = ChatOpenAI(api_key=api_key, model='meta-llama/Meta-Llama-3.1-70B-Instruct-Turbo')

```

3. Preparation of Corpus:
   - Upload the corpus of legal petitions from Google Drive and filter texts with less than **XXX** tokens ([Context length - Together.AI](https://docs.together.ai/docs/chat-models)).

4. Classification and Generation of Summaries:
   - Use customized methods (**Direct-Approach**, **Centroids**, **Descriptions** and **Summary**) to classify and summarize legal texts.
  
5. Metrics and Visualizations:
   - Calculate metrics such as precision, recall, F1-score, AUC-ROC, AUC-PR, and MCC.
   - Visualize results using bar charts, histograms, and confusion matrices.
  
6. Saving the Results:
   - Save results, including classifications, metrics reports, and confusion matrices, directly to Google Drive.

7. Credits
   - This project was developed by **Eng. Willgnner Ferreira Santos** [Lattes](http://lattes.cnpq.br/3203020327904139), **Prof. Dr. Arlindo Rodrigues Galvão Filho** [Lattes](http://lattes.cnpq.br/7744765287200890), and **Prof. Dr. Sávio Salvarino Teles de Oliveira** [Lattes](http://lattes.cnpq.br/1905829499839846), as part of a study on the evaluation of large language models for classifying legal documents in portuguese.
 

















