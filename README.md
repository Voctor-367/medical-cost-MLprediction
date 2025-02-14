# Previsão de Custos de Seguro Médico com Machine Learning

[![Status](https://img.shields.io/badge/status-concluído-brightgreen)]
<!-- Adicione badges relevantes, como status do projeto, build, licença, etc. -->

Este repositório contém o código e a documentação de um projeto de machine learning que visa prever os custos individuais de seguro médico com base em características demográficas e de saúde. O projeto utiliza um conjunto de dados disponível publicamente no Kaggle e explora diferentes modelos de regressão para alcançar o objetivo.

## 1. Visão Geral do Projeto

Este projeto foi desenvolvido como um estudo de caso para aplicar técnicas de aprendizado de máquina na área de seguros de saúde.  O objetivo principal é construir um modelo de regressão que possa estimar com precisão os custos médicos individuais, dados os atributos dos segurados.  Essa previsão pode ser útil para seguradoras em diversas tarefas, como:

*   Precificação de planos de seguro.
*   Estimativa de riscos e reservas financeiras.
*   Identificação de fatores de custo e oportunidades de intervenção (programas de bem-estar, medidas de preservação de saúde etc.).
*   Personalização de ofertas de seguros.

## 2. Conjunto de Dados (Dataset)

O conjunto de dados utilizado neste projeto foi obtido do Kaggle: [Medical Insurance Cost](https://www.kaggle.com/datasets/gauravduttakiit/medical-insurance-cost?select=Train_Data.csv). Ele contém as seguintes variáveis:

*   **age:** Idade do beneficiário principal (inteiro).
*   **sex:** Gênero do segurado (feminino, masculino).
*   **bmi:** Índice de Massa Corporal (IMC) (kg/m²).
*   **children:** Número de filhos/dependentes cobertos pelo seguro.
*   **smoker:** Indicador se o segurado é fumante (sim, não).
*   **region:** Área residencial do segurado nos EUA (northeast, southeast, southwest, northwest).
*   **charges:** Custos médicos individuais cobrados pelo seguro saúde (variável alvo - numérica).


## 3. 📂 Tecnologias Utilizadas

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-2E6E91?style=for-the-badge&logo=seaborn&logoColor=white)
![Optuna](https://img.shields.io/badge/Optuna-EE4C2C?style=for-the-badge&logo=optuna&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-EC4D27?style=for-the-badge&logo=xgboost&logoColor=white)
![CatBoost](https://img.shields.io/badge/CatBoost-151515?style=for-the-badge&logo=catboost&logoColor=white)

*   **Pandas:** Para manipulação e análise de dados.
*   **NumPy:** Para operações numéricas e computação científica.
*   **Scikit-learn:** Para construção, treinamento e avaliação de modelos de machine learning.
*   **Matplotlib e Seaborn:** Para visualização de dados.
*   **Plotly:** Para visualizacoes interativas.
*   **Optuna:** Para otimização de hiperparâmetros.
*   **XGBoost e Catboost**: Para modelos de Gradient Boosting.
*   **RandomForest**: Como modelo para regressão baseado em esemble Bagging.
*   **LinearRegression**: Como modelo para regressão linear.
*   **OneHotEnconder**: Para tratamento de variáveis categóricas.


## 4. Estrutura do Repositório

O repositório está organizado da seguinte forma:

*   **`/` (raiz):**
    *   `medical-cost-MLprediction.ipynb`: Jupyter Notebook principal contendo todo o código do projeto, desde a análise exploratória até a avaliação do modelo final.
    *   `README.md`: Este arquivo, fornecendo a documentação do projeto.
    *   `Train_Data.csv`: Dataset utilizado no projeto.
    *   `Insights.md`: Possui mais detalhes sobre: O desempenho do modelo, as variáveis do dataset e o plano de negócios.S



## 📖 Metodologia e Fluxo de Trabalho

### 🔍 Análise Exploratória de Dados (EDA)
- Utilização de histogramas, gráficos de barras, gráficos de dispersão, violin plots, e matriz de correlação para entender a distribuição das variáveis, identificar outliers e padrões relevantes.

### ⚙️ Pré-processamento dos Dados
- Codificação de variáveis categóricas (One-Hot Encoding).
- Divisão dos dados em conjuntos de treinamento e teste.

### 🤖 Modelagem
- **Modelos testados:**
  - Regressão Linear
  - Random Forest
  - XGBoost
  - CatBoost
- Treinamento e Validação Cruzada utilizando **Stratified K-Fold** para evitar overfitting.
- **Métricas utilizadas:**
  - MAE (Erro Absoluto Médio)
  - MSE (Erro Quadrático Médio)
  - RMSE (Raiz do Erro Quadrático Médio)
  - R² (Coeficiente de Determinação)
  - MAPE (Erro Percentual Absoluto Médio)

### 🎯 Otimização de Hiperparâmetros
- Utilização da biblioteca **Optuna** para otimizar hiperparâmetros do modelo **Random Forest**.
- Definição do espaço de busca para **n_estimators, max_depth, min_samples_split, min_samples_leaf**.
- Execução de múltiplos trials para minimizar o MSE na validação cruzada.

### 🏗️ Feature Engineering
- Criação de uma feature **age_smoker** (idade x tabagismo) para capturar efeitos combinados, mas sem melhora significativa.

## 📊 Resultados e Conclusões

### 🔥 Melhor Modelo: Random Forest

| Métrica | Valor | Desvio Padrão | 
|---------|--------|--------
| MAE | 1544.74 | 55.8158 |
| R² | 0.8957 | 0.0103 |
| MSE | 11972494.86 | 754370.7486 |
| MAPE | 0.1522 | 0.0132 |

### 🔧 Hiperparâmetros Otimizados
- **n_estimators:** 400
- **max_depth:** 14
- **min_samples_split:** 3
- **min_samples_leaf:** 2

### 📌 Principais Conclusões
- **Ser fumante** é o fator mais relevante para o aumento dos custos médicos.
- **Idade e IMC** também possuem forte influência.
- **Número de filhos** tem impacto menor.
- **Região de residência** não apresentou influência significativa.

## 🚀 Plano de Ação
- **Acompanhamento médico** para idosos, com exames preventivos.
- **Medidas contra o tabagismo**, como suporte clínico e psicológico.
- **Acompanhamento nutricional** para evitar obesidade, incluindo consultas e incentivos para prática esportiva.

## ⚠️ Limitações e Próximos Passos
- **Valores extremos:** O modelo pode ter dificuldades em prever custos extremamente altos, com um resíduo maior, pois custos altos no geral não estão bem distribuídos, o que dificultou o modelo a generalizar nesses casos.
- **Variáveis não incluídas:** Não há dados sobre doenças preexistentes, histórico familiar ou hábitos de saúde detalhados.

## 📜 Licença
Este projeto é licenciado sob a **MIT License**. Sinta-se à vontade para usar e contribuir! 🛠️

