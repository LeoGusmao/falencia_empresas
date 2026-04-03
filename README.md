# Projeto de Previsão de Falência de Empresas

## Visão Geral

Este projeto foi desenvolvido como trabalho de conclusão de curso na disciplina de Fundamentos de Machine Learning. O objetivo é prever se uma empresa irá falir ou não com base em indicadores financeiros presentes no conjunto de dados.

A variável alvo do problema é a coluna `Bankrupt?`, em que:

- `0` representa empresa não falida
- `1` representa empresa falida

Trata-se de um problema de classificação supervisionada binária, pois o dataset já possui a resposta correta para cada empresa e o modelo aprende a relacionar os atributos financeiros com a classe final.

## Objetivo do Estudo

O foco principal do trabalho é aplicar corretamente os fundamentos de Machine Learning vistos na disciplina, com atenção especial para:

- pré-processamento dos dados
- análise exploratória
- comparação entre modelos de classificação
- tratamento de classes desbalanceadas
- busca de melhores hiperparâmetros com `GridSearchCV`
- interpretação das métricas, principalmente na identificação de empresas falidas
- análise de overfitting, estabilidade e uso de PCA

## Estrutura do Projeto

Os principais arquivos do projeto são:

- `falencia_empresas.ipynb`: notebook principal com todas as etapas do estudo
- `archive/data.csv`: base de dados utilizada
- `Etapas.md`: roteiro das etapas planejadas para o projeto
- `Enunciado.txt`: orientações e critérios do trabalho
- `AGENTS.md`: regras de condução e edição do projeto

## Etapas do Notebook

O notebook está organizado de forma sequencial e didática, cobrindo:

1. importações e carregamento dos dados
2. conhecimento inicial da base
3. análise exploratória inicial
4. limpeza e preparação inicial
5. pré-processamento
6. rodada de modelos base sem balanceamento
7. rodada de modelos base com `SMOTE`
8. otimização do melhor modelo da estratégia escolhida
9. PCA e escolha da dimensionalidade
10. rodada de modelos base com PCA
11. otimização do melhor modelo com PCA
12. comparação final e conclusão

## Abordagem Utilizada

Durante o estudo, foram comparados diferentes modelos de classificação, com foco em identificar a melhor alternativa para o problema de falência. Como a base apresenta desbalanceamento entre empresas falidas e não falidas, o projeto também avalia o efeito do uso de `SMOTE`.

Além da acurácia, a análise prioriza métricas importantes para a identificação de empresas falidas, como:

- `recall`
- `f1-score`
- diferença entre treino e teste
- diferença entre os resultados da validação cruzada

Essas medidas ajudam a interpretar:

- capacidade real de identificar falências
- estabilidade dos modelos
- sinais de overfitting

## Resultado Geral do Estudo

Pelos resultados obtidos no notebook, a trilha com `SMOTE` mostrou melhor capacidade de identificar empresas falidas do que a trilha sem tratamento de desbalanceamento. Na comparação final, a solução sem PCA apresentou desempenho mais adequado do que a versão com PCA para o objetivo principal do projeto.

De forma geral, o estudo indica que a melhor abordagem foi:

- uso de `SMOTE`
- modelo `Random Forest` otimizado
- solução final sem PCA

## Como Abrir e Executar

1. Abra o projeto no VS Code ou em outro ambiente compatível com Jupyter Notebook.
2. Abra o arquivo `falencia_empresas.ipynb`.
3. Selecione o kernel ou interpretador correto do ambiente Python.
4. Execute as células em ordem, respeitando a sequência das etapas.

## Observação Importante

Mais importante do que a complexidade do modelo, este projeto prioriza a aplicação correta dos fundamentos da disciplina, a interpretação das métricas e a justificativa das escolhas feitas ao longo do estudo.
