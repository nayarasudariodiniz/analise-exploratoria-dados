# 🌍 World Happiness Report: Uma Abordagem Analítica e Estatística

Este projeto apresenta uma Análise Exploratória de Dados (EDA) profunda e a construção de um modelo de Regressão Linear baseado no **World Happiness Report 2019**. O objetivo central foi investigar o impacto do desenvolvimento econômico (PIB) na percepção de felicidade, considerando nuances regionais e desafios estatísticos como a multicolinearidade.

## 📌 Principais Etapas do Projeto

* **Ingestão de Dados via CLI:** Download automatizado do dataset diretamente do Kaggle via linha de comando.
* **Enriquecimento de Dados:** Integração (*join*) com dados de 2015 para segmentação geográfica por regiões, permitindo análises comparativas mais ricas.
* **Análise de Distribuição e Normalidade:** Aplicação do teste de **Shapiro-Wilk** para validar a viabilidade de modelos lineares.
* **Visualização Avançada:** Uso de Boxplots, Histogramas com KDE, Gráficos de Violino e Heatmaps para identificar padrões e *outliers*.
* **Tratamento de Artefatos Estatísticos:** Exclusão estratégica de regiões com amostras insuficientes ($N=2$) que geravam correlações espúrias de $-1.0$.
* **Diagnóstico de Multicolinearidade:** Uso de `pairplot` regional para identificar variáveis redundantes (como Saúde e PIB), garantindo a escolha da melhor variável preditora.
* **Modelagem Preditiva:** Implementação de Regressão Linear Simples via `statsmodels` com análise de $R^2$ e resíduos.

## 📊 Insights Extraídos

* **O PIB como Motor:** O modelo demonstrou que o PIB per capita explica aproximadamente **60% da variação da felicidade global**.
* **Heterogeneidade Regional:** A "força" do dinheiro na felicidade varia drasticamente: é altíssima no Oriente Médio ($r=0.85$) e baixa no Sul da Ásia ($r=0.34$), sugerindo que outros pilares culturais dominam o bem-estar nessas regiões.
* **Efeito Guarda-Chuva:** O PIB demonstrou forte colinearidade com Expectativa de Vida e Suporte Social, atuando como um catalisador de múltiplos indicadores.

## 🛠️ Tecnologias e Bibliotecas

* **Linguagem:** Python 3.12
* **Manipulação:** Pandas e NumPy
* **Visualização:** Seaborn e Matplotlib
* **Estatística:** Scipy (`shapiro`, `pearsonr`) e Statsmodels (`OLS`)

## 📂 Como Replicar

1.  Clone este repositório.
     ```bash
     git clone [https://github.com/nayarasudariodiniz/analise-exploratoria-dados.git](https://github.com/nayarasudariodiniz/analise-exploratoria-dados.git)
     cd analise-exploratoria-dados
2.  Crie e ative um ambiente virtual:
    ```bash
    # Windows
      python -m venv .venv
      .venv\Scripts\activate
      
    # Linux/Mac
      python3 -m venv .venv
      source .venv/bin/activate
3. Instale as dependências
    ```bash
    pip install --upgrade pip
    pip install -r requirements.txt
4.  Execute o notebook: Abra o seu editor favorito (VS Code, Jupyter Lab, etc.) e execute: `01_eda_world_hapiness.ipynb`.

## 🚀 Próximos Passos Sugeridos

* Expansão para análise de série temporal (2015-2022).
* Inclusão de variáveis qualitativas para melhorar o $R^2$ em regiões com baixa correlação econômica.
