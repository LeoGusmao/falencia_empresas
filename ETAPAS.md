# Etapas do estudo de Machine Learning com `data.csv`

## 1. Importação e carregamento dos dados

Objetivo: iniciar o ambiente e carregar a base para análise.

- Importar as bibliotecas principais para manipulação de dados, visualização e pré-processamento.
- Ler o arquivo `archive/data.csv` em um DataFrame.
- Confirmar se a leitura foi feita corretamente.

## 2. Inspeção inicial da base

Objetivo: entender a estrutura geral do conjunto de dados.

- Exibir as primeiras linhas com `head()`.
- Verificar o tamanho da base com `shape`.
- Listar colunas e tipos de dados.
- Listar todas as colunas.
- Para colunas `object` e `category`, verificar a quantidade de valores únicos.
- Se uma coluna `object` ou `category` tiver até 5 valores únicos, listar esses valores.
- Para colunas numéricas com até 5 valores únicos, listar esses valores, pois podem representar flags ou categorias codificadas.
- Identificar a coluna target, isto é, a variável que indica falência da empresa.

## 3. Verificação da variável target

Objetivo: confirmar qual coluna representa o problema de classificação.

- Localizar a coluna que informa se a empresa faliu ou não.
- Verificar os valores possíveis dessa coluna.
- Confirmar se o target está em formato adequado para modelagem.

## 4. Limpeza inicial dos dados

Objetivo: corrigir problemas básicos antes da análise.

- Procurar colunas irrelevantes, duplicadas ou com nomes inconsistentes.
- Verificar registros duplicados.
- Avaliar se existem valores incoerentes ou fora do padrão esperado.

## 5. Análise exploratória simples (EDA)

Objetivo: obter uma visão inicial da distribuição dos dados.

- Gerar estatísticas descritivas das variáveis numéricas.
- Observar o comportamento geral das principais colunas.
- Fazer uma análise visual simples para entender dispersão e possíveis outliers.

## 6. Verificação de valores nulos

Objetivo: medir o impacto de dados faltantes na base.

- Contar os valores nulos por coluna.
- Identificar quais variáveis possuem maior volume de ausência.
- Avaliar se os nulos exigem tratamento antes do treino.

## 7. Distribuição do target

Objetivo: entender o balanceamento entre empresas falidas e não falidas.

- Exibir a contagem de classes do target.
- Criar um gráfico simples mostrando a distribuição da variável alvo.
- Verificar se existe desbalanceamento relevante entre as classes.

## 8. Visualização simples com boxplot

Objetivo: inspecionar a dispersão e detectar possíveis outliers.

- Criar boxplots para variáveis numéricas relevantes.
- Exibir as variáveis em blocos, para não poluir a visualização.
- Permitir parametrizar a faixa de colunas exibidas, por exemplo com coluna inicial e final.
- Comparar amplitude, mediana e presença de valores extremos.
- Considerar que variáveis em escalas muito diferentes podem dificultar a leitura no mesmo gráfico.
- Incluir, quando necessário, uma visualização complementar com variáveis padronizadas apenas para comparação visual entre escalas diferentes.
- Gerar uma tabela com quantidade e percentual de outliers por coluna usando um critério simples, como IQR.
- Usar essa etapa como apoio para decisões simples de limpeza.

## 9. Pré-processamento mínimo

Objetivo: preparar a base para a etapa de modelagem sem complexidade excessiva.

- Separar variáveis preditoras (`X`) e variável target (`y`).
- Garantir que apenas colunas adequadas sigam para o modelo.
- Ajustar tipos de dados quando necessário.

## 11. Padronização dos dados

Objetivo: colocar as variáveis numéricas na mesma escala.

- Aplicar `StandardScaler` nas variáveis de entrada.
- Fazer a padronização de forma compatível com treino e teste.
- Evitar vazamento de dados durante essa etapa.

## 12. Separação entre treino e teste

Objetivo: preparar o conjunto final para avaliação do modelo.

- Dividir os dados em treino e teste.
- Definir proporção adequada para a separação.
- Garantir reprodutibilidade com uma semente fixa.

## 13. Encerramento da preparação

Objetivo: finalizar uma base pronta para os próximos modelos.

- Confirmar dimensões finais de `X_train`, `X_test`, `y_train` e `y_test`.
- Verificar se o pipeline básico de preparação foi concluído sem inconsistências.
- Deixar o conjunto pronto para a etapa seguinte de treinamento de modelos.
