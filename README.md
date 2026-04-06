# Classificação de Sentimentos em Reviews de Texto

Este repositório contém a implementação de um modelo de **classificação de sentimentos em textos**, desenvolvido como parte de um experimento de **mineração de dados e aprendizado de máquina aplicado à análise de opiniões**.

O projeto utiliza **features linguísticas e léxicas extraídas dos textos** e um modelo de **Support Vector Machine (SVM)** para prever a **avaliação (rating)** associada a cada review.

---

## 📁 Estrutura do Projeto

```
├── rating_prediction.ipynb
├── data/
│   └── sentilex.txt
│   └── test.csv
│   └── train.csv
└── README.md
```

* **rating_prediction.ipynb** → Notebook contendo todo o processo de análise, extração de features, treinamento e avaliação do modelo
* **README.md** → Documentação do projeto

---

## ⚙️ Descrição do Projeto

O objetivo do projeto é desenvolver um modelo capaz de **classificar automaticamente o sentimento de reviews de texto**, atribuindo um **rating** com base no conteúdo textual.

Para isso, são extraídas diversas **características linguísticas, emocionais e estruturais** do texto, que são utilizadas como entrada para um modelo de **aprendizado supervisionado**.

O modelo final é treinado utilizando um **SVM com kernel RBF**, escolhido por sua capacidade de modelar **fronteiras de decisão não lineares**.

---

## 🔎 Etapas do Processamento

### 🔸 Preparação dos Dados

Inicialmente, os dados são carregados e separados em:

* **Texto da review**
* **Rating associado**

Os textos passam por um processo de pré-processamento básico, incluindo:

* Conversão para **minúsculas**
* Separação em **tokens (palavras)**

Esse processamento facilita a extração das características utilizadas pelo modelo.

---

### 🔸 Extração de Features

Diversas **features baseadas em linguagem e emoção** são extraídas dos textos, incluindo:

* **Contagem de palavras positivas**
* **Contagem de palavras negativas**
* **Score de sentimento baseado em léxicos**
* **Razão entre palavras positivas e negativas**
* **Diversidade lexical**
* **Comprimento médio das palavras**
* **Contagem de emojis**
* **Uso de letras maiúsculas**
* **Contagem de exclamações e perguntas**
* **Presença de palavras de negação**
* **Intensidade emocional do texto**

Também são utilizadas métricas baseadas em **léxicos de sentimento**, como:

* **SentiLex**
* **VADER Sentiment Analyzer**

Essas features permitem capturar **aspectos semânticos e emocionais** do texto sem utilizar representações tradicionais como TF-IDF.

---

### 🔸 Escalonamento das Features

Após a extração, as features numéricas são normalizadas utilizando **padronização (StandardScaler)**.

Esse processo ajusta os dados para terem:

* média igual a **0**
* desvio padrão igual a **1**

Isso melhora o desempenho de modelos baseados em distância, como o **SVM**.

---

### 🔸 Treinamento do Modelo

O modelo utilizado foi:

* **Support Vector Machine (SVM)**
* **Kernel RBF (Radial Basis Function)**

Durante o treinamento foi realizado um **Grid Search** para encontrar os melhores hiperparâmetros:

* **C** – controla a penalização de erros
* **gamma** – controla a influência dos pontos de treinamento

O treinamento utiliza **validação cruzada (cross-validation)** para estimar a capacidade de generalização do modelo.

---

### 🔸 Avaliação do Modelo

Após o treinamento, o modelo é avaliado utilizando métricas de classificação, como:

* **Acurácia**
* **Distribuição das classes previstas**
* **Análise do comportamento do modelo nas diferentes categorias de rating**

Também é gerado um gráfico de **distribuição dos ratings previstos**, permitindo observar o comportamento do classificador.

---

### 🔸 Predição em Dados de Teste

O modelo treinado é aplicado ao conjunto de **teste**, produzindo as predições de rating para cada review.

As predições são armazenadas em um arquivo para posterior análise e interpretação dos resultados.

---

## 🧰 Tecnologias Utilizadas

* **Python**
* **NumPy** – operações numéricas
* **Pandas** – manipulação de dados
* **Matplotlib** – visualização de gráficos
* **Scikit-learn** – implementação do modelo SVM, normalização e Grid Search
* **NLTK / VADER** – análise de sentimento baseada em léxicos
* **Regex (re)** – extração de padrões no texto

---

## 👥 Autores

| [<img src="https://github.com/thiagocordeirum.png?size=100" width=100><br><sub>Thiago Cordeiro</sub>](https://github.com/thiagocordeirum) | [<img src="https://github.com/EnzoAvila05.png?size=100" width=100><br><sub>Enzo Ávila</sub>](https://github.com/EnzoAvila05) |
|:---:|:---:|

---

## 📅 Informações do Projeto

* Área: **Mineração de Dados / Processamento de Linguagem Natural**
* Orientador: **Tiago de Melo**
* Ano: **2026**
