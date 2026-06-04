# Predição da Intenção de Compra de Clientes em Loja Virtual

## 🛒 Identificando Clientes com Maior Probabilidade de Comprar Online

Neste projeto foi desenvolvido um sistema de **Machine Learning** capaz de prever a intenção de compra de clientes em uma plataforma de e-commerce com base em informações demográficas, comportamentais e histórico de consumo.

O objetivo é identificar quais clientes possuem maior probabilidade de realizar compras online, permitindo que empresas direcionem campanhas de marketing, personalizem ofertas e utilizem seus recursos de forma mais eficiente.

Para isso, foram comparados dois modelos de classificação supervisionada:

* Random Forest
* Regressão Logística

---

## 📌 Contexto de Negócio

Empresas de comércio eletrônico coletam diariamente uma grande quantidade de dados sobre seus clientes.

Transformar esses dados em informações acionáveis pode gerar vantagens competitivas importantes, como:

* Melhor segmentação de campanhas.
* Aumento das taxas de conversão.
* Redução de custos de marketing.
* Personalização da experiência do cliente.

Neste cenário, a capacidade de prever a intenção de compra se torna uma ferramenta estratégica para apoiar a tomada de decisão.

---

## 🎯 Objetivos do Projeto

* Identificar padrões associados à compra online.
* Construir modelos capazes de prever a intenção de compra dos clientes.
* Comparar diferentes algoritmos de classificação.
* Avaliar a robustez dos modelos utilizando validação cruzada.
* Interpretar fatores relacionados ao comportamento de consumo.

---

## 📊 Conjunto de Dados

A base utilizada contém informações demográficas, socioeconômicas e comportamentais dos clientes.

### Exemplos de Variáveis

* Ano de nascimento
* Escolaridade
* Estado civil
* Renda anual
* Número de filhos
* Gastos com diferentes categorias de produtos
* Número de compras presenciais
* Número de visitas ao site
* Histórico de compras

### Variável Alvo

A variável utilizada como alvo foi:

**WebPurchases**

Indicando a ocorrência de compras realizadas pela internet.

---

## 🔎 Análise Exploratória dos Dados

A etapa exploratória teve como objetivo compreender o perfil dos clientes e identificar possíveis relações entre as variáveis.

### 💰 Renda e Consumo

Foi observada uma relação positiva entre renda anual e gastos em categorias como:

* Vinhos
* Carnes
* Compras presenciais

Clientes com rendas mais elevadas tendem a apresentar maior volume de consumo.

### 👨‍👩‍👧 Perfil Familiar

A maioria dos clientes não possui filhos.

Além disso, clientes sem filhos apresentaram, em média, rendas superiores às daqueles que possuem crianças em casa.

### 🌐 Visitas ao Site

Os dados indicaram que clientes com menor renda realizam mais visitas ao site.

Esse comportamento sugere diferentes padrões de consumo e pesquisa entre os grupos analisados.

---

## 🧹 Preparação dos Dados

### Tratamento de Valores Ausentes

A variável de renda (`Income`) apresentava registros faltantes.

Os valores ausentes foram preenchidos utilizando a mediana da distribuição.

### Tratamento de Categorias Raras

Algumas categorias de estado civil possuíam quantidade muito pequena de observações.

Essas categorias foram removidas para evitar ruídos durante a modelagem.

### Remoção de Outliers

Foi aplicado o método **IQR (Interquartile Range)** para identificar e remover valores extremos nas variáveis:

* Income
* MntWines
* MntMeatProducts

Essa etapa reduziu a influência de observações atípicas sobre a análise.

### Codificação de Variáveis Categóricas

Foram utilizadas duas estratégias:

#### Education

Transformação ordinal através de mapeamento manual dos níveis educacionais.

#### Marital Status

Aplicação de One-Hot Encoding utilizando `get_dummies()`.

### Padronização

As variáveis numéricas foram padronizadas utilizando **StandardScaler**.

---

## 📉 Seleção de Variáveis

Após a construção da matriz de correlação, foram removidas variáveis com baixa relevância para o problema.

Entre elas:

* Ano de nascimento
* Educação
* Recência
* Reclamações
* Algumas categorias de estado civil

Essa etapa buscou simplificar o modelo e reduzir ruídos.

---

## 🤖 Modelagem

Foram avaliados dois algoritmos de classificação.

### 🌲 Random Forest

O Random Forest foi utilizado em sua configuração padrão.

O modelo foi treinado diretamente sobre os dados originais de treino.

### 📈 Regressão Logística

Para a Regressão Logística foi aplicado previamente o método **SMOTE**, visando balancear as classes e reduzir possíveis vieses causados pelo desbalanceamento dos dados.

---

## 📈 Avaliação dos Modelos

Os modelos foram avaliados utilizando:

* Precision
* Recall
* F1-Score
* Matriz de Confusão
* Cross Validation (10 Folds)

---

## ✅ Resultados

### Random Forest

O modelo apresentou o melhor desempenho geral.

Principais destaques:

* Mais de 90% de acerto na identificação da intenção de compra.
* Apenas 11 clientes que realmente comprariam online deixaram de ser identificados.
* Excelente equilíbrio entre precisão e recall.

### Regressão Logística

Apesar de apresentar desempenho inferior ao Random Forest, a Regressão Logística também obteve resultados consistentes.

O modelo alcançou aproximadamente:

* 85% de acurácia média.
* 87% de precisão nas previsões positivas.

---

## 🔄 Validação Cruzada

Para avaliar a capacidade de generalização dos modelos, foi utilizada validação cruzada com 10 folds.

Os resultados mostraram desempenho consistente em diferentes subconjuntos dos dados, indicando que os modelos apresentam boa robustez e baixo risco de dependência excessiva de uma única divisão treino-teste.

---

## 💡 Aplicações Práticas

Uma solução semelhante poderia ser utilizada para:

### Marketing Direcionado

Identificar clientes com maior probabilidade de conversão.

### Campanhas Promocionais

Priorizar públicos mais propensos à compra.

### Programas de Fidelização

Detectar perfis com maior potencial de retenção.

### Recomendação de Produtos

Personalizar ofertas com base no comportamento do consumidor.

---

## 🛠️ Tecnologias Utilizadas

### Linguagem

* Python

### Bibliotecas

* Pandas
* NumPy
* Scikit-Learn
* Seaborn
* Matplotlib
* Imbalanced-Learn

### Algoritmos

* Random Forest Classifier
* Logistic Regression
* SMOTE
* K-Fold Cross Validation

---

## 🎓 Principais Aprendizados

Durante o desenvolvimento deste projeto foram aplicados conceitos importantes de Ciência de Dados, incluindo:

* Análise exploratória de dados.
* Tratamento de valores ausentes.
* Remoção de outliers.
* Engenharia e seleção de atributos.
* Codificação de variáveis categóricas.
* Balanceamento de classes.
* Classificação supervisionada.
* Comparação de modelos.
* Validação cruzada.

O projeto demonstra como dados comportamentais e demográficos podem ser transformados em previsões úteis para apoiar estratégias de marketing e tomada de decisão orientada por dados.
