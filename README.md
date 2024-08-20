# Evaluation of Large Language Models for Classifying Legal Documents in Portuguese

This project evaluates the application of Large Language Models (LLMs) in the classification of legal documents, with a focus on the Public Defender's Office of the State of Goiás (DPE-GO). Utilizing a Brazilian legal corpus, traditional transformer-based models were compared with advanced LLMs. Various prompt construction methods were employed to assess the models' effectiveness. The results demonstrate that LLMs, especially Sabia-3 and Mixtral-8x22B-Instruct-v0.1, outperform traditional models, achieving accuracy of up to **100%** and **99.42%** respectively. We conclude that the integration of LLMs can significantly increase efficiency and standardization in the analysis of legal texts, providing effective support to public defenders.

The repository includes four types of developed prompts: summaries, descriptions, direct classification, and the use of centroids. Other LLMs were used, where the main difference lies in the model loading and the configuration of the context length supported by the selected LLM. The fine-tuning of BERTimBau Base is also available; other BERTs were used, with differences in the loading structure of these BERTs. The training, testing, and validation corpus was used in the BERTs, and finally, the test corpus was used in the LLMs to verify the extent to which the results improved.

## Prerequisites

- **Python 3.8+**
- **Google Colab** (or local environment with Jupyter Notebook)
- **API Key** to access the model `Sabia-3` and `Mixtral-8x22B-Instruct-v0.1`

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
  - Configure ChatOpenAI with your desired API key and template. The LLMs available from the [Maritaca AI](https://www.maritaca.ai/) and [Together.AI](https://docs.together.ai/docs/chat-models).

**Sabia-3**

```bash
api_key = 'YOUR_API_KEY'
def get_sabia_response(messages, max_tokens=100, temperature=0.7, model="sabia-3"):
    request_data = {
        "messages": messages,
        "do_sample": True,
        'max_tokens': max_tokens,
        "temperature": temperature,
        "model": model,
    }
    response = requests.post(
        url,
        json=request_data,
        headers=auth_header
    )
```

**Mixtral-8x22B-Instruct-v0.1**

```bash

from langchain_openai import ChatOpenAI

api_key = 'YOUR_API_KEY'
llm = ChatOpenAI(api_key=api_key, model='mistralai/Mixtral-8x22B-Instruct-v0.1').

```

3. Preparation of Corpus:
   - Upload the corpus of legal petitions from Google Drive and filter texts with less than **XXX** tokens ([Comprimento do contexto - Maritaca AI](https://docs.maritaca.ai/pt/modelos)) and ([Comprimento do contexto - Together.AI](https://docs.together.ai/docs/chat-models)).

4. Classification and Generation of Summaries:
   - Use customized prompts (PROMPT_CLASSIFICATION, PROMPT_SUMMARY, PROMPT_DESCRIPTION) to classify and summarize legal texts.
  
5. Metrics and Visualizations:
   - Calculate metrics such as precision, recall, F1-score, AUC-ROC, AUC-PR, and MCC.
   - Visualize results using bar charts, histograms, and confusion matrices.
  
6. Saving the Results:
   - Save results, including classifications, metrics reports, and confusion matrices, directly to Google Drive.

7. Credits
   - This project was developed by **Eng. Willgnner Ferreira Santos** [Lattes](http://lattes.cnpq.br/3203020327904139), **Prof. Dr. Arlindo Rodrigues Galvão Filho** [Lattes](http://lattes.cnpq.br/7744765287200890), and **Prof. Dr. Sávio Salvarino Teles de Oliveira** [Lattes](http://lattes.cnpq.br/1905829499839846), as part of a study on the evaluation of large language models for classifying legal documents in portuguese.
 























