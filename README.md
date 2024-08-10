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
```

1. Montar o Google Drive:
   - O projeto requer acesso ao Google Drive para carregar datasets e salvar resultados.
   - Execute o seguinte comando no Colab:

O projeto requer acesso ao Google Drive para carregar datasets e salvar resultados.
Execute o seguinte comando no Colab:

```bash
from google.colab import drive
drive.mount('/content/drive')
```

2. Configuração do Modelo:
   - Configure o ChatOpenAI com a chave da API e o modelo desejado:

 ```bash
from langchain_openai import ChatOpenAI

api_key = 'SUA_API_KEY'
llm = ChatOpenAI(api_key=api_key, model='mistralai/Mixtral-8x22B-Instruct-v0.1')
```
3. Preparação dos Dados:
   - Carregue o dataset de petições jurídicas a partir do Google Drive e filtre os textos com menos de 60.000 tokens.

4. Classificação e Geração de Resumos:
   - Utilize prompts customizados (PROMPT_CLASSIFICACAO, PROMPT_RESUMO, PROMPT_DESCRICAO) para classificar e resumir os textos jurídicos.
  
5. Métricas e Visualizações:
   - Calcule métricas como precisão, recall, f1-score, AUC-ROC, AUC-PR, e MCC.
   - Visualize os resultados utilizando gráficos de barras, histogramas, e matrizes de confusão.
  
5. Salvando os Resultados:
   - Salve os resultados, incluindo classificações, relatórios de métricas, e matrizes de confusão, diretamente no Google Drive.

## Estrutura do Projeto

 ```bash
LLMs/
├── classificacoes_centroids/
│   ├── classification_report_centroids.csv
│   ├── classificacoes_centroids.csv
│   └── classificacoes_centroids.xlsx
├── Texto-centroids/
│   ├── centroids.csv
│   └── centroids.xlsx
└── Matriz-confusao/
    ├── matriz_de_confusao.csv
    ├── matriz_de_confusao.xlsx
    ├── matriz_de_confusao_normalizada.csv
    └── matriz_de_confusao_normalizada.xlsx
```

6. Créditos
   - Este projeto foi desenvolvido por [Seu Nome] como parte de um estudo sobre a aplicação de modelos de linguagem de grande porte para a classificação automática de textos jurídicos. O modelo Mixtral-8x22B-Instruct-v0.1 foi utilizado com o suporte da API langchain_openai.




















