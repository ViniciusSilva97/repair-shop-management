# Segurança, privacidade e recuperação

## 1. Objetivos

- impedir perda silenciosa de dados;
- limitar ações conforme função;
- proteger credenciais e backups;
- tornar alterações críticas rastreáveis;
- reduzir exposição na rede local;
- permitir suporte sem coleta excessiva;
- preparar atendimento a obrigações de privacidade.

## 2. Modelo de ameaças inicial

| Risco | Controles principais |
| --- | --- |
| Furto ou perda do computador | senha do Windows, proteção de disco recomendada, sessão do app, backup protegido. |
| Funcionário acessando módulo indevido | usuários individuais, funções, autorização no servidor. |
| Exclusão ou fraude interna | auditoria, inativação, justificativa, dupla confirmação. |
| Ransomware ou falha de disco | backups rotativos, cópia externa, teste de restauração. |
| Estação falsa na rede | pareamento temporário, identidade de dispositivo, revogação. |
| XML ou anexo malicioso | parser seguro, limites, tipos permitidos, armazenamento não executável. |
| Atualização adulterada | assinatura, hash e canal de atualização autenticado. |
| Vazamento em logs/suporte | minimização, redação e consentimento. |
| Corrupção em queda de energia | transações, modo de journal adequado, fsync/política testada, recuperação. |

## 3. Autenticação e autorização

- senha com hash moderno e parâmetros versionados;
- usuário inicial criado no assistente, sem senha padrão;
- bloqueio progressivo contra tentativas repetidas sem facilitar negação de serviço;
- sessão expira ou bloqueia conforme política;
- servidor valida toda permissão crítica;
- ações como estorno, restauração e revogação exigem perfil adequado;
- estação possui credencial diferente da conta humana;
- segredos locais usam armazenamento protegido do sistema quando aplicável.

## 4. Perfis iniciais

| Perfil | Acesso típico |
| --- | --- |
| Administrador | configuração, usuários, restauração e auditoria. |
| Proprietário/Gerente | operação completa e relatórios, sem acesso técnico desnecessário. |
| Atendente | clientes, veículos, orçamento e acompanhamento. |
| Técnico | histórico, diagnóstico, execução e evidências. |
| Caixa | recebimentos, fechamento e relatórios permitidos. |
| Estoque | produtos, compras, inventário e movimentos. |
| Consulta | leitura limitada. |

Permissões serão granulares; perfis são modelos editáveis controlados.

## 5. Auditoria

Registrar:

- autenticação e bloqueio;
- criação/inativação de usuário;
- mudança de permissão;
- alteração de ordem finalizada;
- autorização e recusa;
- movimento e ajuste de estoque;
- estorno e fechamento de caixa;
- importação e conflito de XML;
- backup, restauração e migração;
- pareamento/revogação de estação;
- exportação sensível.

Auditoria é append-only pela aplicação. Deve permitir consulta por entidade, usuário e período, com retenção definida.

## 6. Privacidade

Antes da venda, realizar revisão profissional da LGPD e dos documentos contratuais. Requisitos de produto:

- coletar somente dados necessários;
- indicar finalidade dos campos opcionais;
- restringir exibição por função;
- permitir exportação estruturada;
- documentar correção, inativação e descarte quando aplicável;
- não usar dados do cliente para treinar modelos ou publicidade sem base e autorização adequadas;
- não enviar telemetria identificável por padrão;
- registrar consentimentos ou bases operacionais quando o fluxo exigir;
- controlar dados do proprietário anterior do veículo.

## 7. Backups

### Conteúdo

- banco;
- XMLs;
- anexos;
- configurações necessárias;
- manifesto com versão, hashes e data;
- metadados de criptografia sem incluir a chave.

### Política inicial

- backup automático diário;
- backup antes de atualização e restauração;
- retenção configurável com padrão seguro;
- recomendação de cópia em unidade externa ou local sincronizado;
- nunca considerar pasta no mesmo disco como única proteção;
- status visível ao administrador.

### Consistência

Não copiar arquivo de banco aberto de maneira ingênua. Usar mecanismo de backup consistente do banco. SQLite oferece API de backup online para produzir snapshot consistente.

## 8. Restauração

1. Autenticar administrador.
2. Selecionar backup e validar manifesto, hashes, versão e espaço.
3. Explicar impacto e desconectar estações.
4. Criar backup preventivo do estado atual quando possível.
5. Restaurar em área temporária.
6. Verificar banco e anexos.
7. Trocar estado ativo de modo atômico.
8. Executar migração necessária.
9. Registrar auditoria e relatório.

O teste de restauração fará parte da rotina de qualidade; “backup criado” não significa “backup recuperável”.

## 9. Continuidade

- **RPO inicial:** no máximo um dia útil de dados em política padrão; possibilidade de backup adicional no fechamento.
- **RTO inicial:** restauração assistida em até duas horas no cenário de referência.
- metas serão ajustadas após pilotos;
- falha do principal interrompe estações, mas não deve corromper dados confirmados;
- sincronização multi-principal não faz parte da 1.0.

## 10. Logs e pacote de suporte

Logs técnicos terão rotação, limite e níveis. Não registrar senhas, tokens, XML completo, documentos ou anexos. Campos pessoais serão omitidos ou mascarados quando não necessários.

O pacote de suporte incluirá diagnóstico, versões, códigos de erro e trechos técnicos revisados. O usuário visualiza o que será exportado e autoriza a ação.

## 11. Checklist de liberação de segurança

- revisão de permissões e endpoints;
- teste de elevação de privilégio;
- parser XML endurecido;
- anexos fora de caminhos executáveis;
- segredos ausentes do repositório e logs;
- dependências e licenças inventariadas;
- instalador e atualização assinados;
- restauração validada;
- regras de firewall mínimas;
- revogação de estação testada;
- vulnerabilidades críticas resolvidas;
- política de resposta a incidentes publicada.

## 12. Referências oficiais

- [API de backup do SQLite](https://sqlite.org/backup.html)
- [Autenticação por host do PostgreSQL](https://www.postgresql.org/docs/current/auth-pg-hba-conf.html)
- [SSL no PostgreSQL](https://www.postgresql.org/docs/current/libpq-ssl.html)

