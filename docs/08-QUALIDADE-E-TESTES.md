# Qualidade e estratégia de testes

## 1. Princípio

O produto guarda histórico técnico, estoque e dinheiro. Testes priorizam integridade e recuperação antes de quantidade de telas.

## 2. Pirâmide de testes

### Unidade

- estados e transições de ordem;
- autorização e recusa;
- cálculos decimais;
- conversão de unidade;
- saldo derivado;
- políticas de garantia;
- permissões;
- normalização de identificadores.

### Integração

- repositórios SQLite e PostgreSQL aplicáveis;
- migrações Alembic;
- transações e rollback;
- armazenamento de anexos;
- importação XML;
- backup e restauração;
- geração de PDF.

### Contrato

- cliente/API;
- compatibilidade entre versões;
- idempotência;
- erros e validações;
- autenticação de estação e usuário.

### Sistema/UI

- instalação limpa;
- assistente inicial;
- fluxo completo da ordem;
- importação de compra;
- fechamento de caixa;
- promoção para rede;
- reparo e atualização;
- restauração em máquina limpa.

## 3. Cenários críticos obrigatórios

1. Duas estações tentam consumir a última unidade.
2. Conexão cai após enviar finalização de ordem e antes da resposta.
3. Aplicação fecha durante importação de lote.
4. Energia é interrompida durante escrita simulada.
5. Atualização falha depois do backup e antes da migração completa.
6. XML duplicado possui bytes diferentes.
7. Ordem finalizada recebe tentativa de edição sem permissão.
8. Usuário revogado mantém uma sessão aberta.
9. Estação incompatível tenta gravar.
10. Disco fica sem espaço durante anexo ou backup.
11. Backup está truncado ou adulterado.
12. Relógio de uma estação está incorreto.

## 4. Dados de teste

- dados sintéticos, sem documentos pessoais reais;
- fábricas de cliente, veículo, ordem e movimentos;
- amostras fiscais autorizadas ou anonimizadas;
- casos com acentos, nomes longos e valores-limite;
- placa ausente, quadro duplicado informado e dados incompletos;
- base pequena para testes rápidos e base de carga versionada.

## 5. Desempenho

Cenário inicial de referência:

- 20 mil veículos;
- 50 mil ordens;
- 10 mil itens de catálogo;
- 250 mil movimentos de estoque;
- 100 mil lançamentos financeiros;
- 10 estações simultâneas;
- hardware de piloto com SSD e 8 GB de RAM ou perfil posteriormente declarado.

Medir:

- pesquisa de cliente/veículo;
- abertura de histórico paginado;
- gravação de ordem;
- reserva/consumo de estoque;
- importação de 100 XMLs;
- fechamento de caixa;
- backup e restauração.

Meta inicial: percentil 95 de operações comuns em até dois segundos na rede local de referência. Processos longos mostram progresso e podem ser retomados/cancelados com segurança.

## 6. Compatibilidade

Matriz antes da 1.0:

- versões de Windows e arquiteturas oficialmente suportadas;
- escalas de exibição 100%, 125%, 150% e 200%;
- resolução mínima declarada;
- teclado e leitores de código quando aplicável;
- caminhos com acentos;
- usuário Windows sem privilégio administrativo após instalação;
- redes com DHCP e mudança de endereço;
- firewall padrão e softwares de segurança comuns no piloto.

## 7. Acessibilidade e usabilidade

- fluxo completo somente por teclado;
- ordem previsível de foco;
- contraste e estados não dependentes apenas de cor;
- mensagens que indiquem problema e ação;
- confirmação reforçada somente em ações perigosas;
- termos da oficina, não termos de banco ou API;
- teste moderado com usuários reais.

## 8. CI e portas de qualidade

Cada alteração:

- formatação e lint;
- verificação de tipos;
- unidade e integração afetadas;
- verificação de migração;
- análise de dependências;
- geração de artefato em branch de liberação.

Release candidate:

- testes de sistema em máquina limpa;
- assinatura e checksum;
- restauração;
- atualização desde versões suportadas;
- carga e concorrência;
- inspeção de licenças;
- teste exploratório do fluxo principal.

## 9. Severidade de defeitos

| Nível | Exemplo | Regra de liberação |
| --- | --- | --- |
| Crítico | perda/corrupção, acesso indevido, cálculo financeiro grave | bloqueia qualquer release. |
| Alto | fluxo principal impossível, backup não restaura | bloqueia release comercial. |
| Médio | alternativa existente com impacto moderado | exige decisão explícita e prazo. |
| Baixo | texto, alinhamento ou inconveniência pequena | pode entrar no backlog. |

## 10. Piloto

Realizar em etapas:

1. ambiente controlado com dados sintéticos;
2. oficina parceira em paralelo ao método atual;
3. mais de um perfil de oficina;
4. edição em rede com duas ou mais estações;
5. migração, atualização e recuperação reais supervisionadas.

Durante piloto, medir tempo de tarefa, erros, pedidos de suporte, falhas de rede, volume de dados e compreensão dos termos.

