# Contexto operacional para IA

## Missão

Auxiliar no desenvolvimento de um sistema desktop comercial para pequenas oficinas de automóveis, motocicletas e bicicletas. O produto é offline-first, usa Python/PySide6 e oferece modo individual e modo em rede local.

## Leitura obrigatória

Antes de propor ou alterar código:

1. `README.md`;
2. `docs/02-REQUISITOS.md`;
3. documento do módulo afetado;
4. `docs/04-ARQUITETURA.md`;
5. `docs/09-ROADMAP-COMERCIAL.md`.

## Decisões invariantes atuais

- histórico do veículo é o centro da experiência;
- relato, inspeção, diagnóstico e solução são distintos;
- ordens finalizadas não sofrem edição silenciosa;
- estoque é razão de movimentações, não saldo editado diretamente;
- custo médio ponderado móvel é o método gerencial padrão da versão 1.0;
- rotação física por antiguidade/validade é independente do método de valoração;
- fluxo de caixa realizado e projetado é requisito comercial P0 e não equivale à DFC contábil;
- XML original é preservado e tratado como entrada não confiável;
- SQLite nunca é compartilhado diretamente por arquivo na rede;
- estações usam API/serviço e não acessam banco diretamente;
- instalação e atualização preservam dados por padrão;
- exclusão de dados é fluxo separado e protegido;
- o produto não realiza contabilidade formal ou emissão fiscal na 1.0;
- a aplicação funciona sem internet;
- o cliente não configura ferramentas de desenvolvimento, banco ou IP no fluxo normal;
- valores monetários usam decimal;
- operações críticas usam transação e idempotência.

## Regras de mudança

- não adicionar escopo de versão posterior sem registrar decisão;
- não alterar regra de negócio apenas para facilitar uma tela;
- não acoplar domínio a PySide6, FastAPI ou SQLAlchemy;
- não introduzir nova dependência sem avaliar manutenção, licença, empacotamento e segurança;
- atualizar requisitos, testes e documentação junto com código;
- criar migração para mudança de schema;
- preservar compatibilidade e dados de versões já distribuídas;
- registrar decisões arquiteturais significativas em ADR.

## Processo para implementar uma funcionalidade

1. Identificar IDs de requisito.
2. Escrever critérios de aceite e cenários de erro.
3. Modelar invariantes no domínio.
4. Definir contrato do caso de uso.
5. Implementar portas e infraestrutura.
6. Criar UI sem duplicar regra.
7. Testar unidade, integração e fluxo.
8. Verificar auditoria, permissões, backup e migração.
9. Atualizar documentação e notas de versão.

## Perguntas que exigem confirmação humana

- mudança de preço, licença ou edição;
- inclusão de emissão fiscal ou interpretação tributária;
- coleta de telemetria ou dados externos;
- exclusão física ou retenção de dados;
- suporte oficial a sistema operacional;
- escolha definitiva de banco da edição em rede;
- alteração de fluxo validado por oficinas;
- adiamento de requisito P0;
- ação destrutiva em repositório ou dados.

## Padrão de resposta técnica

Ao propor uma mudança, informar:

- objetivo do usuário;
- requisitos atendidos;
- arquivos/camadas afetados;
- riscos de integridade e segurança;
- migração necessária;
- testes necessários;
- documentação atualizada;
- o que permanece fora do escopo.

## Definições rápidas

- **Principal:** computador que hospeda serviço, dados e backups na rede local.
- **Estação:** computador cliente conectado ao principal.
- **Histórico:** projeção cronológica rastreável de fatos do veículo.
- **Auditoria:** registro de quem fez ação crítica e qual foi a mudança.
- **Log técnico:** diagnóstico de funcionamento; não substitui auditoria.
- **Documento fiscal importado:** evidência recebida; não significa lançamento confirmado.
- **Diário da Oficina:** registro operacional; não é Livro Diário contábil.

## Estado atual

O projeto está na fase de documentação e validação de produto. Não presumir que repositório, código, marca, schemas ou instalador já existem. O próximo marco previsto é 0.1.0 — Fundação.
