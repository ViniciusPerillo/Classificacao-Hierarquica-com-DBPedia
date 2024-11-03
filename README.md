# Classificação Hierárquica com DBPedia

Este repositório contém o trabalho realizado para a disciplina de Aprendizado de Máquina 2 na Universidade Federal de São Carlos (UFSCar). O projeto aborda a classificação hierárquica de textos da Wikipedia usando a base de dados DBPedia, focando na comparação entre técnicas de classificação plana e hierárquica.

## Objetivo

Realizar a classificação hierárquica de textos em múltiplos níveis de classes (L1, L2 e L3), explorando diferentes modelos e técnicas de pré-processamento para maximizar a precisão das previsões. A classificação hierárquica possibilita uma análise mais profunda, considerando a estrutura das classes de forma integrada.

## Base de Dados

A base utilizada é composta por textos da Wikipedia e está disponível no Kaggle. A estrutura do dataset inclui:

- **text**: Texto completo de uma página da Wikipedia.
- **l1**: Categoria de nível 1 (classe genérica).
- **l2**: Categoria de nível 2 (classe intermediária).
- **l3**: Categoria de nível 3 (classe mais específica).

## Pré-Processamento

Para preparar o texto para o treinamento, aplicamos as seguintes etapas:

1. **Tokenização**: Segmentação dos textos em palavras e símbolos.
2. **Remoção de Stopwords**: Filtragem de palavras irrelevantes.
3. **Lematização**: Simplificação das palavras à sua forma raiz.
4. **Word Embedding**: Representação das palavras em vetores, utilizando o modelo GloVe pré-treinado.

## Modelos

Duas abordagens de classificação foram utilizadas:

1. **Classificação Plana**: Desconsidera os níveis hierárquicos, classificando diretamente em L3.
2. **Classificação Local por Pai**: Constrói modelos hierárquicos para classificar primeiro L1, depois L2 e, por fim, L3.

### Algoritmos de Classificação

Utilizamos os algoritmos de Regressão Logística e Random Forest para cada uma das abordagens, com os seguintes parâmetros:

- **Regressão Logística**: `max_iter=1000`
- **Random Forest**: `n_estimators=100`, `random_state=42`

## Resultados

Os modelos foram avaliados usando F1-Score, Precisão e Recall. A seguir estão os principais resultados:

- **Classificação Plana**:
  - **Regressão Logística**: F1-Score: 0.8849
  - **Random Forest**: F1-Score: 0.8364

- **Classificação Hierárquica** (com 50 dimensões para Word Embedding):
  - **Regressão Logística**: F1-Score: 0.7959
  - **Random Forest**: F1-Score: 0.8398

Para uma análise mais detalhada, consulte o relatório completo.

## Conclusão

A classificação plana apresentou um desempenho superior, porém com alto custo computacional. A técnica hierárquica com Random Forest e Word Embedding de 50 dimensões demonstrou uma boa performance, conciliando precisão e custo computacional.

## Como Executar

1. Clone o repositório:
   ```bash
   git clone <url_do_repositorio>
   cd <nome_do_repositorio>
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Execute o notebook:

## Referências

- **DBPedia Dataset**: [Kaggle](https://www.kaggle.com/datasets/danofer/dbpedia-classes)
- **Modelo GloVe**: Pennington, Socher e Manning (2014).

## Autores

- Ana Ellen Deodato P Silva
- Vinicius de Oliveira Guimarães
- Vinícius Gonçalves Perillo
