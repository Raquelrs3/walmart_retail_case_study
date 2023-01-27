# Previsão de Vendas Supermercado Walmart
![220314-walmart-plus-vl-2x1](https://user-images.githubusercontent.com/98356094/215175084-f1bfc7ce-a06e-4245-9579-586fbb93827c.jpeg)

Este é um projeto realizado com dados públicos disponibilizados pela empresa na plataforma do [KAGGLE](https://www.kaggle.com/competitions/walmart-retail-case-study2/data).


## 1. Problema de Negócio
O Walmart tem uma política de promoções ao longo do ano, principalmente em datas que precedem feriados importantes.
Dessa forma, precisam validar as promoções e sua efetividade.

### O negócio está interessado em saber:
- Qual é o impacto dos feriados e promoções nas vendas das lojas?
- Existe algum setor que desempenhe melhor?
- É possível estimar as vendas das lojas por semana em datas futuras de 2012–11–02 a 2013–07-26? Se sim, quais seriam esses valores?


## 2. Entendimento do Negócio
#### Motivação
A equipe de negocio precisa entender como estão os resultados de venda das semanas seguintes para validar as campanhas de promoção anuais da rede de varejo Walmart.

#### Causa Raiz do Problema
Entender se está ocorrendo retorno financeiro com as campanhas de vendas durante os feriados e promoções anuais.

#### Quem é o Stakeholder
Equipe de negocios do Walmart.

#### Formato da Solução
* Vendas diárias em R$, por semana,
* Problema de predição,
* Time series, regressão...,
* Modelo de Predição.
 
 
## 3. Metodologia de Desenvolvimento do Projeto
 O projeto foi desenvolvido através da técnica CRISP-DM
 * Versão END-TO_END da solução,
 * Velocidade na entrega de valor,
 * Mapeamento de todos os possíveis problems.


##### Passo 01 - Descrição dos dados: Conhecimento dos dados, tipos, métricas estatísticas para identificar outliers, analise das métricas estatísticas e ajustes em features do dataset (preenchimento de NA's).


##### Passo 02 - Feature Engineering: Desenvolvimento de mapa mental para analisar o fenômeno, as variáveis e os principais aspectos que impactam cada uma delas. 


##### Passo 03 - Filtragem dos dados: Filtragem das linhas e excluir as colunas que não são relevantes para o modelo ou não fazem parte do escopo do negócio. EX: Dias em que as lojas estavam fevhadas ou inoperantes.


##### Passo 04 - Análise Exploratória dos dados: Exploração dos dados para encontrar insights.


##### Passo 05 - Preparação dos dados: Preparação para as aplicações de modelos de machine learning.


##### Passo 06 - Seleção de Features: Seleção dos melhores atributos para treinar o modelo. Utilizamos o algoritmo Boruta para essa seleção.


##### Passo 07 - Modelagem de Machine Learning: Foram realizados testes e treinamentos de alguns modelos de machine learning, para possibilitar a comparação da performance e escolha do modelo ideal para o projeto. Foi utilizada a técnica de Cross Validation para garantir a performance real sobre os dados selecionados.


##### Passo 08 - Hyperparameter Fine Tunning: Análise pelo método Random Search, em cima do algoritmo escolhido XBoost, para escolha dos melhores valores de cada parâmetro do modelo.


##### Passo 09 - Tradução e interpretação de erros: Aqui entendemos a performance do modelo para comunicar ao CFO quanto em dinheiro o modelo retornará à empresa. Foram usadas as métricas: MAE (Mean Absolute Error), MAPE (Mean Absolute Percentage Error) e RMSE (Root Mean Squared Error).


## 4. Entendendo os Dados
* Dados disponibilizados pela empresa na plataforma do [Kaggle](https://www.kaggle.com/competitions/walmart-retail-case-study2/data) 

| VARIÁVEL  |  DEFINIÇÃO  |
| ------------------- | ------------------- |
|  Store	 |  Código da loja.|
|  Date |  Semanas de vendas.|
|  Weekly_Sales	|Vendas por loja.|
|  Holiday_Flag	|Se a semana é um feriado especial semana. 1 – Semana de feriado, 0 – Semana sem feriado.|
| Temperature |Temperatura do dia da venda|
| Fuel_Price |Custo de gasolina na região.|
| CPI |Índice de preços ao consumidor.|
| Unemployment |Taxa de desemprego.|

## 5. Principais Insights

**Hipótese 1**
Lojas abertas durante período de feriados importantes deveriam vender mais.

!![Screen Shot 2023-01-27 at 16 15 07](https://user-images.githubusercontent.com/98356094/215176452-eb4683b1-b358-4da6-af4a-f582b83a6a4b.png)


**Hipótese 2**
Setor de lojas tipo A tem melhores resultados com vendas.

![Screen Shot 2023-01-27 at 16 16 36](https://user-images.githubusercontent.com/98356094/215176822-5bd7546d-216b-4689-9c67-a4818b651389.png)


**Hipótese 3**
Dias mais quentes tendem a vender menos.

![Screen Shot 2023-01-27 at 16 18 23](https://user-images.githubusercontent.com/98356094/215177561-f5a9ac60-c276-4469-adc6-8d452dedbcdd.png)


## 6. Performance do Modelo

A estratégia foi usar modelos lineares com o propósito de relacionar duas variáveis (resposta e explicativa) como também modelos não lineares que permitem ajustes de relações mais complexas. Desta forma, respectivamente, podemos determinar se as médias dos grupos são diferentes e as causas de variação, como também, fazer predições fora do domínio observado de uma variável(x).

Para a realização desta etapa do projeto, foram aplicados os seguintes modelos:

* Modelos Lineares
* Média,
* Linear Regression Regularized.

* Modelos Não Lineares
* Random Forest Regressor,
* XGBoost Regressor.


### Comparação da performance dos modelos

![Screen Shot 2023-01-27 at 16 24 29](https://user-images.githubusercontent.com/98356094/215179419-1336bb55-0671-4585-85f3-95eec9b1a9ef.png)


### Performance final do modelo escolhido após Cross Validation

![Screen Shot 2023-01-27 at 16 21 44](https://user-images.githubusercontent.com/98356094/215178946-582d9002-9bb0-4545-a428-bdf8d8ca2d82.png)


## 7. Resultado Final
Obtivemos bons resultados na previsão de vendas, o qual a equipe de negócios poderá validar as campanhas de vendas durante os feriados.
A performance do modelo pode ser constatada na análise da relação entre as vendas e as predições:

![Screen Shot 2023-01-27 at 16 48 33](https://user-images.githubusercontent.com/98356094/215183798-e6fbbe45-2b77-4c82-b252-d07d1f52c490.png)
![Screen Shot 2023-01-27 at 16 48 24](https://user-images.githubusercontent.com/98356094/215183858-54bdc6c8-1ad0-4dfa-9a1b-2ba56b0a8f1c.png)


## - Conclusão
 
As vendas das próximas semanas estão sendo projetadas com sucesso. Sendo assim, a equipe de negócio poderá consultar as predições das vendas, podendo extrair informações do rendimento das lojas para melhores tomadas de decisão.
