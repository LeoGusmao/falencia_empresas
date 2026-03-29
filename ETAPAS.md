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

## 6. Rodada de modelos base

Objetivo: comparar vários algoritmos de forma padronizada para eleger o melhor ponto de partida.

- Definir uma função de apoio, como `criacao_modelo`, para concentrar a criação, o treino e a avaliação inicial dos modelos.
- Rodar 5 modelos base sobre a mesma base pré-processada.
- Para cada modelo, observar métricas iniciais de treino, teste e validação cruzada.
- Exibir resultados de forma padronizada para facilitar a comparação.
- Eleger o melhor modelo base sem PCA.

## 7. Otimização do melhor modelo sem PCA

Objetivo: melhorar o melhor modelo encontrado na base original.

- Aplicar `GridSearchCV` no melhor modelo base.
- Buscar os melhores hiperparâmetros.
- Avaliar o modelo otimizado na base sem PCA.
- Registrar os resultados para comparação posterior.

## 8. PCA e escolha da dimensionalidade

Objetivo: criar uma segunda trilha de estudo com redução de dimensionalidade.

- Aplicar PCA sobre a base já preparada para modelagem.
- Gerar o gráfico da variância explicada acumulada.
- Usar uma técnica visual, como a do joelho, para apoiar a escolha do número de componentes.
- Definir a quantidade de componentes a ser usada na trilha com PCA.

## 9. Rodada de modelos base com PCA

Objetivo: repetir a comparação de modelos na base transformada por PCA.

- Aplicar novamente os 5 modelos base, agora sobre os dados com PCA.
- Reutilizar a lógica da função `criacao_modelo` para manter a avaliação consistente.
- Comparar os resultados dos modelos com PCA.
- Eleger o melhor modelo base com PCA.

## 10. Otimização do melhor modelo com PCA

Objetivo: melhorar o melhor modelo encontrado na trilha com PCA.

- Aplicar `GridSearchCV` ao melhor modelo da base com PCA.
- Buscar os melhores hiperparâmetros nessa nova configuração.
- Avaliar o modelo otimizado com PCA.
- Registrar os resultados para comparação com a trilha sem PCA.

## 11. Comparação final e conclusão

Objetivo: consolidar o estudo e decidir qual abordagem foi melhor.

- Comparar o melhor modelo otimizado sem PCA com o melhor modelo otimizado com PCA.
- Observar ganhos, perdas e diferenças nas métricas principais.
- Registrar a conclusão final do estudo e a abordagem escolhida.
