# Cape_Town_Reviews

Projeto de grupo de **Tópicos Avançados em Data Mining** (Mestrado em Ciência de Dados e Gestão, 2026/2027).

Análise dos comentários de hóspedes Airbnb de **Cape Town** (Inside Airbnb) com text mining e classificação de anúncios de alta qualidade.

- **Parte I:** text mining dos comentários (qualidade dos dados, idioma, sentimento com VADER e RoBERTa, tópicos com LDA e BERTopic, variáveis de texto por anúncio).
- **Parte II:** modelos supervisionados (Naive Bayes, Random Forest, SVM) para identificar anúncios de alta qualidade, com e sem variáveis de texto.

## Estrutura
```
projeto_airbnb_cape_town.ipynb   # notebook principal (Partes I e II)
requirements.txt                 # dependências
annotation/                      # conjunto de validação manual do sentimento (anotado pelo grupo)
data/                            # dados originais (não versionados — ver abaixo)
outputs/figures/                 # gráficos usados na apresentação
outputs/intermediate/            # ficheiros intermédios da Parte I (regeneráveis; não versionados)
```

## Como reproduzir
1. Descarregar de [Inside Airbnb](https://insideairbnb.com/get-the-data/) os ficheiros **detalhados** de Cape Town (`listings.csv.gz` e `reviews.csv.gz`) e colocá-los em `data/`.
2. Criar o ambiente (Python 3.12):
   ```bash
   uv venv --python 3.12 .venv && uv pip install --python .venv/bin/python -r requirements.txt
   ```
3. Correr o notebook. Os passos mais pesados (deteção de idioma, RoBERTa) guardam cache em `outputs/intermediate/`.
