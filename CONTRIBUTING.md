# Guia de contribuição

## Fluxo obrigatório

Toda mudança deve seguir:

1. Criar ou selecionar uma issue com objetivo e critérios de aceite.
2. Criar branch a partir da `main` atualizada.
3. Implementar somente o escopo da issue.
4. Criar commits pequenos e descritivos.
5. Executar as validações aplicáveis.
6. Abrir pull request em modo draft.
7. Atualizar documentação e testes no mesmo PR.
8. Solicitar revisão quando os critérios estiverem atendidos.
9. Resolver comentários sem apagar o contexto da revisão.
10. Fazer merge somente com checks aprovados e sem conversas pendentes.

Não realizar desenvolvimento diretamente na `main`.

## Branches

Padrão:

```text
agent/<issue>-<descricao-curta>
feature/<issue>-<descricao-curta>
fix/<issue>-<descricao-curta>
docs/<issue>-<descricao-curta>
```

Exemplos:

```text
docs/1-product-foundation
feature/12-vehicle-history
fix/48-stock-idempotency
```

Branches são temporárias e removidas após o merge.

## Commits

Usar verbo no imperativo ou padrão Conventional Commits simplificado:

```text
docs: establish product requirements
feat: add vehicle registration use case
fix: prevent duplicate stock movement
test: cover order authorization transitions
refactor: isolate inventory repository
```

Um commit deve representar uma decisão lógica e permanecer revisável. Não misturar formatação geral, funcionalidade e correção sem relação.

## Issues

Uma issue de funcionalidade deve conter:

- problema do usuário;
- escopo e fora do escopo;
- requisitos relacionados;
- critérios de aceite;
- riscos de dados, segurança e migração;
- dependências.

Defeitos devem incluir versão, impacto, reprodução, resultado esperado, resultado obtido e evidências sem dados pessoais.

## Pull requests

O PR deve:

- referenciar a issue com `Closes #n` quando apropriado;
- explicar o que e por que mudou;
- listar impacto e riscos;
- declarar migrações;
- registrar testes executados;
- atualizar documentação;
- permanecer draft enquanto incompleto.

## Revisão

O revisor verifica, nesta ordem:

1. aderência ao escopo e requisitos;
2. integridade e risco de perda de dados;
3. autorização, privacidade e auditoria;
4. regras de negócio;
5. testes e tratamento de erro;
6. arquitetura e manutenibilidade;
7. interface e documentação.

Comentários devem indicar severidade:

- `blocking`: precisa ser resolvido antes do merge;
- `important`: correção esperada ou decisão registrada;
- `suggestion`: melhoria não bloqueante;
- `question`: precisa de esclarecimento.

## Definition of Done

- critérios de aceite atendidos;
- testes relevantes aprovados;
- migração testada quando houver schema;
- nenhuma credencial ou dado real adicionado;
- logs e mensagens revisados;
- documentação de usuário, desenvolvedor e IA atualizada;
- checks de CI aprovados;
- revisão concluída;
- PR sem conflitos e conversas bloqueantes.

## Mudanças sensíveis

Exigem decisão explícita e revisão reforçada:

- exclusão ou retenção de dados;
- autenticação e permissões;
- estoque, caixa e custo;
- XML fiscal;
- backup, restauração e migração;
- instalador e atualização;
- dependências e licenças;
- telemetria ou integrações externas.

## Licenciamento das contribuições

Ao enviar uma contribuição, o autor declara possuir os direitos necessários e concorda com a seção **Contribuições ao projeto** do arquivo [LICENSE](LICENSE), inclusive com a autorização concedida ao titular para uso comercial e relicenciamento da contribuição. Dependências e materiais de terceiros devem ser identificados e permanecer sob suas licenças originais.
