# 🏠 Projeto de Machine Learning - Precificação de Imóveis (Ames Housing)

![Status](https://img.shields.io/badge/Status-Concluído-green)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/17ggxXenYXxwMvsOkb-xsve4hyAiSZTvl)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)

## 📝 Descrição do Projeto

Este projeto implementa um fluxo completo de Machine Learning Supervisionado para prever o preço de venda de casas na cidade de Ames, Iowa. O objetivo é criar um modelo capaz de estimar valores imobiliários com base em diversas características (físicas, localização, qualidade, etc.), minimizando o erro de previsão (RMSE).

O projeto aborda desde a limpeza de dados e engenharia de atributos até a comparação de modelos avançados de regressão.

## 🚀 Funcionalidades e Técnicas Aplicadas

* **Análise Exploratória e Limpeza:**
    * Remoção de *outliers* (imóveis com área habitável > 4000 sqft).
    * Normalização da variável alvo (`SalePrice`) utilizando transformação logarítmica (`np.log1p`) para corrigir assimetria.
* **Engenharia de Atributos (Preprocessing):**
    * **Numéricos:** Imputação pela mediana e padronização (`StandardScaler`).
    * **Ordinais:** Codificação baseada em hierarquia de qualidade (Ex: *Ex > Gd > TA...*) usando `OrdinalEncoder`.
    * **Nominais:** Codificação *One-Hot* para variáveis categóricas sem ordem.
    * Uso de `Pipeline` e `ColumnTransformer` para evitar *data leakage*.
* **Modelagem (GridSearch):**
    * Regressão Linear
    * Ridge (Regularização L2)
    * Lasso (Regularização L1)
    * Random Forest Regressor

## 📊 Resultados

Após a otimização de hiperparâmetros via validação cruzada (Cross-Validation), os modelos obtiveram os seguintes desempenhos no conjunto de teste:

| Modelo | RMSE (Erro Médio $) | R² |
| :--- | :--- | :--- |
| **Lasso (Campeão)** | **$ 19,211.83** | **0.9297** |
| Ridge | $ 19,775.48 | 0.9255 |
| Regressão Linear | $ 20,749.65 | 0.9180 |
| Random Forest | $ 25,199.45 | 0.8790 |

> O modelo **Lasso** mostrou-se o mais eficiente, conseguindo explicar cerca de **93% da variância** dos preços.

## 🛠️ Tecnologias Utilizadas

* **Python**
* **Pandas & Numpy:** Manipulação de dados.
* **Matplotlib & Seaborn:** Visualização de dados.
* **Scikit-Learn:** Construção de pipelines, modelos e métricas de avaliação.
