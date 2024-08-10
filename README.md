# Classificação de Textos Jurídicos usando LLMs

This project evaluates the application of Large Language Models (LLMs) in the classification of legal documents, with a focus on the Public Defender's Office of the State of Goiás (DPE-GO). Utilizing a Brazilian legal corpus, traditional transformer-based models were compared with advanced LLMs. Various prompt construction methods were employed to assess the models' effectiveness. The results demonstrate that LLMs, particularly the Mixtral-8x22B-Instruct-v0.1, outperform traditional models, achieving an accuracy of up to **99.42%**. We conclude that the integration of LLMs can significantly enhance efficiency and standardization in legal text analysis, providing effective support for public defenders.

The repository includes four types of developed prompts: summaries, descriptions, direct classification, and the use of centroids. Other LLMs were used, where the main difference lies in the model loading and the configuration of the context length supported by the selected LLM. The fine-tuning of BERTimBau Base is also available; other BERTs were used, with differences in the loading structure of these BERTs. The training, testing, and validation corpus was used in the BERTs, and finally, the test corpus was used in the LLMs to verify the extent to which the results improved.

## Prerequisites

- **Python 3.8+**
- **Google Colab** (or local environment with Jupyter Notebook)
- **API Key** to access the model `Mixtral-8x22B-Instruct-v0.1`

## Installation

Install necessary dependencies:

```bash
pip install tiktoken langchain-community langchainhub langchain_openai langchain pandas matplotlib scikit-learn seaborn
```

1. Mount Google Drive:
   - The project required access to Google Drive to load the corpus and save the results.
   - Run the following command in Colab:
     
```bash
from google.colab import drive
drive.mount('/content/drive')
```

2. Model Configuration:
  - Configure ChatOpenAI with your desired API key and template. The LLMs available from the [Together.AI - LLMs](https://docs.together.ai/docs/chat-models).

 ```bash
from langchain_openai import ChatOpenAI

api_key = 'YOUR_API_KEY'
llm = ChatOpenAI(api_key=api_key, model='mistralai/Mixtral-8x22B-Instruct-v0.1')
```
3. Preparation of Corpus:
   - Upload the *corpus* of legal petitions from Google Drive and filter texts with less than **XXX** tokens ([Comprimento do contexto - LLMs](https://docs.together.ai/docs/chat-models)).

4. Classification and Generation of Summaries:
   - Use customized prompts (PROMPT_CLASSIFICATION, PROMPT_SUMMARY, PROMPT_DESCRIPTION) to classify and summarize legal texts.
  
5. Metrics and Visualizations:
   - Calculate metrics such as precision, recall, F1-score, AUC-ROC, AUC-PR, and MCC.
   - Visualize results using bar charts, histograms, and confusion matrices.
  
6. Saving the Results:
   - Save results, including classifications, metrics reports, and confusion matrices, directly to Google Drive.

## Project Structure

 ```bash
LLMs/
├── classifications_summaries/
│   ├── classification_report_summaries.csv
│   ├── classifications_summaries.csv
│   ├── classifications_summaries.xlsx
│   ├── confusion_matrix_summaries.csv
│   ├── normalized_confusion_matrix_summaries.csv
│   └── confusion_matrix_summaries.xlsx
├── classifications_centroids/
│   ├── classification_report_centroids.csv
│   ├── classifications_centroids.csv
│   ├── classifications_centroids.xlsx
│   ├── confusion_matrix_centroids.csv
│   ├── normalized_confusion_matrix_centroids.csv
│   └── confusion_matrix_centroids.xlsx
├── classifications_direct/
│   ├── classification_report_direct.csv
│   ├── classifications_direct.csv
│   ├── classifications_direct.xlsx
│   ├── confusion_matrix_direct.csv
│   ├── normalized_confusion_matrix_direct.csv
│   └── confusion_matrix_direct.xlsx
├── classifications_description/
│   ├── classification_report_description.csv
│   ├── classifications_description.csv
│   ├── classifications_description.xlsx
│   ├── confusion_matrix_description.csv
│   ├── normalized_confusion_matrix_description.csv
│   └── confusion_matrix_description.xlsx
├── Text-centroids/
│   ├── centroids.csv
│   └── centroids.xlsx
└── General-reports/
    ├── comparative_report.xlsx
    ├── overall_results.csv
    └── metrics_comparison.csv
```

7. Credits
   - This project was developed by **Willgnner Ferreira Santos**, **,Arlindo Rodrigues Galvão Filho**, and **,Sávio Salvarino Teles de Oliveira**, as part of a study on the application of LLMs for the classification of legal texts. The `Mixtral-8x22B-Instruct-v0.1` model was used with the support of the langchain_openai API.


























