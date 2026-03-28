# AGENTS.md

## Escopo
1. Respeitar estritamente o escopo pedido.
2. Se o pedido for para mexer em um arquivo, mexer só nele.
3. Não mexer em dois módulos ao mesmo tempo, salvo se o usuário pedir.
4. Não reorganizar arquitetura, nem mover módulos, sem pedido explícito.
5. Não adicionar bibliotecas externas sem autorização.
6. Se o pedido for só análise, não mexer no código.
7. Não fazer ajustes secundários nem ampliar escopo fora da etapa atual.
8. O arquivo `ESTRUTURA.md` existe como referência da estrutura de pastas; só deve ser alterado com autorização do usuário e, nesse caso, deve ser mantido atualizado.
9. O arquivo `AGENTS.md` só deve ser alterado com pedido explícito do usuário; a IA pode sugerir mudanças quando achar necessário.
10. Ao evoluir o `AGENTS.md`, escrever regras explícitas e claras o suficiente para poderem ser reaproveitadas em outros projetos; regras muito específicas devem ir para documentos próprios.
11. Neste projeto, o fluxo principal é de estudo guiado por etapas; refatoração e testes não são padrão, a menos que o usuário peça.

## Simplicidade
1. Preferir sempre a solução mais simples.
2. Evitar abstrações, classes ou padrões complexos quando uma função simples resolver.
3. Em mudanças simples, preferir alterações pequenas.
4. Se a mudança ficar grande, explicar antes e pedir aprovação.
5. Evitar lógicas defensivas no consumidor quando a responsabilidade já pertence ao produtor do dado.

## Execução por etapas
1. Trabalhar uma etapa por vez, seguindo a ordem definida em `ETAPAS.md`, salvo orientação contrária do usuário.
2. Antes de iniciar a próxima etapa, concluir e deixar clara a etapa atual.
3. Não adiantar implementação de etapas futuras sem pedido explícito.
4. Quando o pedido for conceitual, estrutural ou de documentação, não converter automaticamente em código.
5. Em estudos de dados e machine learning, priorizar clareza, sequência didática e rastreabilidade das decisões.
6. Se uma etapa depender de decisão ambígua, apresentar a dúvida de forma objetiva antes de avançar.

## Validação da etapa
1. Nem toda etapa exige testes automatizados.
2. Em etapas de estudo, priorizar validações simples e adequadas ao contexto, como inspeção de dados, conferência de dimensões, tipos, nulos e distribuições.
3. Só propor testes automatizados quando isso fizer sentido para o objetivo da etapa e houver pedido ou benefício claro.
4. Após mudanças em código ou notebook, verificar o resultado mínimo necessário para confirmar que a etapa foi concluída corretamente.
