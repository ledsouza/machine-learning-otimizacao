# Otimização de Modelos de Machine Learning para Predição de Inadimplência
![Static Badge](https://img.shields.io/badge/Status-Finalizado-green)

## Descrição

Este projeto visa otimizar modelos de machine learning supervisionados (Decision Tree Classifier e Logistic Regression) para prever a probabilidade de inadimplência em empréstimos. O processo envolve diversas técnicas de otimização, como validação cruzada aninhada e não aninhada, busca em grid, busca aleatória e busca bayesiana.

## Tecnologias Utilizadas

- **Linguagem:** Python
- **Bibliotecas:**
    - Scikit-learn: Para modelagem, validação cruzada e otimização de hiperparâmetros.
    - Pandas: Para manipulação e análise de dados.
    - NumPy: Para operações numéricas.
    - Plotly: Para visualização de dados.
    - Scikit-optimize: Para busca bayesiana de hiperparâmetros.

## Descrição Detalhada

1. **Preparação dos Dados:**
   - Os dados foram fornecidos já pré-processados, prontos para modelagem.
   - As features incluem informações financeiras do cliente, histórico de crédito, dados demográficos e informações de contato.
   - O target é a variável binária 'inadimplente', indicando se o cliente deixou de pagar o empréstimo.
<img width="1142" alt="image" src="https://github.com/ledsouza/machine-learning-otimizacao/assets/56280624/49e1b6d4-7388-40ef-bc3b-1b7599dda80f">

2. **Modelagem Inicial (Baseline):**
   - Dois modelos foram treinados com hiperparâmetros padrão:
      - Decision Tree Classifier
      - Logistic Regression
   - O desempenho dos modelos foi avaliado para estabelecer um baseline.
<img width="619" alt="image" src="https://github.com/ledsouza/machine-learning-otimizacao/assets/56280624/a8a25e30-cc97-4a7b-ac34-96a3decf3ade">

3. **Validação Cruzada Não Aninhada:**
   - **GridSearchCV:** Uma busca exaustiva em uma grade de hiperparâmetros foi realizada para cada modelo, usando validação cruzada com StratifiedKFold para garantir a representatividade das classes.
   - **RandomizedSearchCV:** Uma busca aleatória em um espaço de hiperparâmetros foi realizada para cada modelo, também com validação cruzada estratificada.
<img width="636" alt="image" src="https://github.com/ledsouza/machine-learning-otimizacao/assets/56280624/376a90fd-73d7-40ee-8843-60507c6191a5">

4. **Validação Cruzada Aninhada:**
   - O processo de busca de hiperparâmetros (GridSearchCV ou RandomizedSearchCV) foi repetido dentro de um loop externo de validação cruzada. Isso ajuda a estimar o desempenho do modelo de forma mais robusta e a evitar o overfitting.
<img width="509" alt="image" src="https://github.com/ledsouza/machine-learning-otimizacao/assets/56280624/209f4fa0-055b-4a90-b7c6-a814c5f80312">

5. **BayesSearchCV Aninhado:**
   - Uma busca bayesiana de hiperparâmetros foi realizada, aproveitando informações de iterações anteriores para otimizar a busca de forma mais eficiente.
<img width="484" alt="image" src="https://github.com/ledsouza/machine-learning-otimizacao/assets/56280624/7d94a584-552e-4b79-8cfd-3b4d26b05b71">

6. **Avaliação e Comparação dos Modelos:**
   - Os melhores modelos de cada etapa foram avaliados em termos da métrica mais relevante: recall.
   - Os resultados foram comparados para identificar as melhores estratégias de otimização e o modelo com o melhor desempenho generalizado.


