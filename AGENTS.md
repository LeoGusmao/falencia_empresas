# AGENTS.md

## Escopo
1. Respeitar estritamente o escopo pedido.
2. Se o pedido for para mexer em um arquivo, mexer só nele.
3. Não mexer em dois módulos ao mesmo tempo, salvo se o usuário pedir.
4. Não reorganizar arquitetura, mover módulos ou criar arquivos e pastas principais sem pedido explícito.
5. Não adicionar bibliotecas externas sem autorização.
6. Se o pedido for só análise, não mexer no código.
7. Não fazer ajustes secundários nem ampliar escopo fora da etapa atual.
8. O `ESTRUTURA.md` só deve ser alterado com autorização do usuário e, nesse caso, deve ser mantido atualizado.
9. O `AGENTS.md` só deve ser alterado com pedido explícito do usuário.
10. Neste projeto, o fluxo principal é de estudo guiado por etapas; refatoração e testes não são padrão, salvo pedido do usuário.

## Simplicidade
1. Preferir sempre a solução mais simples.
2. Em mudanças simples, preferir alterações pequenas.
3. Evitar abstrações, classes ou padrões complexos quando uma função simples resolver.
4. Se a mudança ficar grande, explicar antes e pedir aprovação.
5. Preferir nomes de variáveis em português nas partes autorais do código do projeto, salvo nomes próprios de bibliotecas, métodos e APIs externas.
6. Em notebooks, preferir fluxo linear, didático e fácil de acompanhar, saídas visuais e diretas em vez de muitos `prints` explicativos.
7. Em verificações simples de dados, mostrar apenas o necessário para a etapa.
8. Criar funções auxiliares apenas quando houver repetição clara e relevante, sem esconder o processo principal do estudo.

## Execução por etapas
1. Trabalhar uma etapa por vez, seguindo a ordem definida em `Etapas.md`, salvo orientação contrária do usuário.
2. Antes de iniciar a próxima etapa, concluir e deixar clara a etapa atual.
3. Não adiantar implementação de etapas futuras sem pedido explícito.
4. Quando o pedido for conceitual, estrutural ou de documentação, não converter automaticamente em código.
5. Em estudos de dados e machine learning, priorizar clareza, sequência didática e rastreabilidade das decisões.
6. Se uma etapa depender de decisão ambígua, apresentar a dúvida de forma objetiva antes de avançar.
7. Ao editar notebooks, manter células curtas, focadas e proporcionais ao objetivo da etapa.
8. Quando a etapa pedir uma limpeza simples, aplicar a limpeza diretamente e exibir apenas o que foi alterado.
9. Em etapas de modelagem, manter estrutura padronizada de avaliação para facilitar comparação entre modelos.

## Validação
1. Nem toda etapa exige testes automatizados.
2. Em etapas de estudo, priorizar validações simples, como inspeção de dados, dimensões, tipos, nulos, distribuições e métricas do modelo.
3. Só propor testes automatizados quando isso fizer sentido para o objetivo da etapa e houver pedido ou benefício claro.
4. Após mudanças em código ou notebook, verificar o resultado mínimo necessário para confirmar que a etapa foi concluída corretamente.
5. Em notebooks, preferir tabelas, `display()` e gráficos simples quando isso comunicar melhor do que texto corrido.

## Notebooks
1. Ao editar arquivos `.ipynb`, considerar que o VS Code pode manter uma versão antiga da aba em memória mesmo após alteração externa no disco.
2. Se um notebook foi alterado externamente, orientar o usuário a recarregar o arquivo antes de salvar para evitar sobrescrever mudanças.
3. Quando houver risco de confusão entre código atual e saída antiga, limpar ou reduzir outputs salvos no notebook quando isso ajudar a leitura.
