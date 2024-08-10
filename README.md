# Classificação de Textos Jurídicos usando LLMs

Este projeto implementa um pipeline de classificação de textos jurídicos utilizando o modelo `Mixtral-8x22B-Instruct-v0.1` via API e diversas técnicas de processamento de texto. O objetivo principal é categorizar petições processuais em uma das 24 classes predefinidas.

## Pré-requisitos

- **Python 3.8+**
- **Google Colab** (ou ambiente local com Jupyter Notebook)
- **API Key** para acesso ao modelo `Mixtral-8x22B-Instruct-v0.1`

## Instalação

Instale as dependências necessárias:

```bash
pip install tiktoken langchain-community langchainhub langchain_openai langchain pandas matplotlib scikit-learn seaborn

Como Rodar
Montar o Google Drive:

O projeto requer acesso ao Google Drive para carregar datasets e salvar resultados.
Execute o seguinte comando no Colab:

from google.colab import drive
drive.mount('/content/drive')
