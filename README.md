# Evaluation of Large Language Models for Classifying Legal Documents in Portuguese

The growing procedural demand in legal institutions has led to work overload, impacting the efficiency of the judicial system. This scenario, worsened by the limitation of human resources, highlights the need for technological solutions that speed up the processing and analysis of documents. In view of this reality, this work proposes a pipeline for automating the classification of these documents, evaluating four methods of representing legal texts at the pipeline input: original text, summaries, centroids, and document descriptions. The pipeline was developed and tested at the Public Defender’s Office of the State of Goiás (DPE-GO). Each approach implements a specific strategy to structure the input texts, aiming to improve the models' ability to interpret and classify legal documents. A new Portuguese-language dataset was introduced, developed for this application, and the performance of Large Language Models (LLMs) was evaluated in classification tasks. The analysis results show that using summaries improves classification accuracy and maximizes the F1-score, optimizing the use of LLMs by reducing the number of processed tokens without compromising precision. These results highlight the impact of textual representations of documents and the potential of LLMs in the automatic classification of legal documents, as in the case of DPE-GO. The contributions of this work indicate that the application of LLMs, combined with optimized textual representations, can increase the productivity and quality of services provided by legal institutions, promoting advances in the overall efficiency of the judicial system.

[Dissertation Link](https://repositorio.bc.ufg.br/tede/items/57a868bd-cc39-403c-8d18-13a4201f5707)

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
   - This project was developed by **MSc. Eng. Willgnner Ferreira Santos** [Lattes](http://lattes.cnpq.br/3203020327904139), **Prof. Dr. Arlindo Rodrigues Galvão Filho** [Lattes](http://lattes.cnpq.br/7744765287200890), and **Prof. Dr. Sávio Salvarino Teles de Oliveira** [Lattes](http://lattes.cnpq.br/1905829499839846), as part of a study on the evaluation of large language models for classifying legal documents in portuguese.
 

















