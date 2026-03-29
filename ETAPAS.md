# Etapas do estudo de Machine Learning com `data.csv`

## 1. Importações e carregamento dos dados

Objetivo: iniciar o ambiente e carregar a base para análise.

- Importar as bibliotecas principais para manipulação de dados, visualização, pré-processamento, modelagem e avaliação.
- Ler o arquivo `archive/data.csv` em um DataFrame.
- Confirmar se a leitura foi feita corretamente.

## 2. Conhecimento inicial da base

Objetivo: entender a estrutura geral do conjunto de dados.

- Exibir as primeiras linhas com `head()`.
- Verificar o tamanho da base com `shape`.
- Gerar `info()` e `describe()`.
- Listar colunas e tipos de dados.
- Identificar a coluna target que indica falência da empresa.
- Verificar os valores possíveis do target e sua contagem.
- Observar colunas categóricas ou numéricas de baixa cardinalidade que mereçam atenção.

## 3. Análise exploratória inicial

Objetivo: obter uma visão inicial da distribuição dos dados e de possíveis problemas.

- Avaliar valores nulos por coluna.
- Verificar a distribuição do target e o possível desbalanceamento entre as classes.
- Fazer gráficos simples para leitura inicial, como histogramas e boxplots.
- Exibir boxplots em blocos de colunas para não poluir a visualização.
- Permitir, quando necessário, uma visualização complementar com variáveis padronizadas apenas para comparação visual entre escalas diferentes.
- Gerar uma tabela com quantidade e percentual de outliers por coluna usando um critério simples, como IQR.

## 4. Limpeza e preparação inicial

Objetivo: corrigir problemas básicos e deixar os dados prontos para separação e modelagem.

- Ajustar nomes de colunas, quando necessário.
- Tratar inconsistências simples identificadas na análise inicial.
- Definir a estratégia de tratamento de valores nulos.
- Separar variáveis preditoras (`X`) e variável target (`y`).
- Dividir os dados em treino e teste com `train_test_split`.
- Garantir reprodutibilidade com uma semente fixa.

## 5. Pré-processamento

Objetivo: preparar os dados de forma adequada para a modelagem.

- Aplicar imputação simples quando houver necessidade.
- Aplicar codificação de variáveis categóricas, se necessário.
- Padronizar variáveis numéricas com `StandardScaler`.
- Organizar essas transformações de forma compatível com treino e teste.
- Evitar vazamento de dados durante essa etapa.

## 6. Rodada de modelos base sem balanceamento

Objetivo: comparar vários algoritmos de forma padronizada na base original de treino.

- Definir uma função de apoio, como `criacao_modelo`, para concentrar a criação, o treino e a avaliação inicial dos modelos.
- Rodar 5 modelos base sobre a mesma base pré-processada, sem técnica de balanceamento.
- Para cada modelo, observar métricas de treino, teste e validação cruzada.
- Registrar a diferença entre a acurácia de treino e a acurácia de teste.
- Exibir os 5 resultados da validação cruzada.
- Registrar a diferença entre o maior e o menor valor da validação cruzada.
- Exibir relatórios completos por modelo e comparar com foco especial na classe `1`.
- Eleger o melhor modelo base sem balanceamento.

## 7. Rodada de modelos base com SMOTE

Objetivo: repetir a comparação de modelos após ampliar a representatividade da classe minoritária no treino.

- Aplicar `SMOTE` apenas sobre os dados de treino.
- Rodar novamente os mesmos 5 modelos base.
- Reutilizar a mesma lógica de avaliação da etapa anterior.
- Exibir relatórios completos por modelo e comparar com foco especial na classe `1`.
- Comparar os resultados da rodada com SMOTE com a rodada sem balanceamento.
- Definir qual trilha seguirá adiante para a otimização.

## 8. Otimização do melhor modelo da estratégia escolhida

Objetivo: melhorar o melhor modelo encontrado na trilha vencedora antes do PCA.

- Aplicar `GridSearchCV` no melhor modelo base da estratégia escolhida.
- Buscar os melhores hiperparâmetros do modelo.
- Quando fizer sentido para o algoritmo, permitir que a otimização teste também opções como `class_weight=None` e `class_weight='balanced'`.
- Manter nessa etapa outras combinações de hiperparâmetros que já façam parte do modelo.
- Avaliar o modelo otimizado.
- Exibir os resultados finais em formato estruturado, destacando a classe `1`.
- Registrar os resultados para comparação posterior.

## 9. PCA e escolha da dimensionalidade

Objetivo: criar uma segunda trilha de estudo com redução de dimensionalidade.

- Aplicar PCA sobre a base já preparada segundo a estratégia vencedora.
- Gerar o gráfico da variância explicada acumulada.
- Usar uma técnica visual, como a do joelho, para apoiar a escolha do número de componentes.
- Definir a quantidade de componentes a ser usada na trilha com PCA.

## 10. Rodada de modelos base com PCA

Objetivo: repetir a comparação de modelos na base transformada por PCA.

- Aplicar novamente os 5 modelos base, agora sobre os dados com PCA.
- Manter a estratégia vencedora escolhida antes do PCA.
- Reutilizar a lógica da função `criacao_modelo` para manter a avaliação consistente.
- Comparar os resultados dos modelos com PCA.
- Exibir relatórios completos por modelo e comparar com foco especial na classe `1`.
- Eleger o melhor modelo base com PCA.

## 11. Otimização do melhor modelo com PCA

Objetivo: melhorar o melhor modelo encontrado na trilha com PCA.

- Aplicar `GridSearchCV` ao melhor modelo da base com PCA.
- Buscar os melhores hiperparâmetros nessa nova configuração.
- Quando fizer sentido para o algoritmo, permitir que a otimização teste também opções como `class_weight=None` e `class_weight='balanced'`.
- Avaliar o modelo otimizado com PCA.
- Exibir os resultados finais em formato estruturado, destacando a classe `1`.
- Registrar os resultados para comparação com a trilha sem PCA.

## 12. Comparação final e conclusão

Objetivo: consolidar o estudo e decidir qual abordagem foi melhor.

- Comparar a melhor abordagem sem PCA com a melhor abordagem com PCA.
- Observar ganhos, perdas e diferenças nas métricas principais.
- Considerar especialmente os resultados da classe `1` na decisão final.
- Registrar a conclusão final do estudo e a abordagem escolhida.
