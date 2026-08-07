# Instalação, rede e atualização

## 1. Objetivo de experiência

O usuário recebe um único arquivo de instalação. Não precisa conhecer Python, banco, API, terminal, portas ou IP fixo.

Mensagem antes da seleção:

> Se o sistema será usado em mais de um computador, todos devem estar conectados à mesma rede local — pelo Wi-Fi ou por cabo no mesmo roteador. Se será usado em apenas um computador, nenhuma configuração de rede é necessária.

## 2. Modos do instalador

### Usar somente neste computador

Instala interface, serviço local, banco, backup, atualização, diagnóstico e atalhos. A estrutura fica preparada para promoção posterior.

### Configurar computador principal

Instala todos os componentes do modo individual e habilita acesso autenticado pela rede local. Gera identificação e código temporário para estações.

### Adicionar este computador à oficina

Instala interface e componentes de estação, procura servidores elegíveis e solicita pareamento. Não instala um segundo banco da oficina.

### Reparar ou reconfigurar

Repara arquivos, atalhos, serviço, descoberta e regras locais necessárias. Não apaga dados.

## 3. Fluxo individual

1. Verificar sistema, arquitetura, espaço e permissões.
2. Exibir licença e local dos dados.
3. Instalar componentes em diretório de programa.
4. Criar diretório de dados separado.
5. Inicializar schema e usuário administrador.
6. Configurar backup.
7. Executar teste de saúde.
8. Abrir assistente inicial.

## 4. Fluxo em rede

### No principal

1. Confirmar que a máquina costuma permanecer ligada.
2. Criar backup se houver instalação individual.
3. Ativar serviço de rede com privilégio mínimo.
4. Configurar regra restrita de firewall.
5. Publicar descoberta local.
6. Gerar código de pareamento curto e expirável.
7. Mostrar nome da oficina e estado do servidor.

### Na estação

1. Procurar servidores na rede.
2. Exibir somente oficinas identificáveis e compatíveis.
3. Usuário escolhe a oficina e informa código.
4. Principal aprova ou política permite pareamento autenticado.
5. Estação recebe credencial própria revogável.
6. Usuário entra com sua conta.

## 5. Descoberta

O produto não deve depender de IP fixo digitado. Usará descoberta local e identificador estável. Entrada manual de hostname/IP será recurso de suporte, não fluxo padrão.

Redes de convidados, isolamento de clientes, VLANs ou dois roteadores podem bloquear descoberta. O diagnóstico deve explicar em linguagem comum:

> Os computadores parecem estar em redes diferentes ou impedidos de conversar. Conecte ambos à mesma rede principal ou solicite ajuda ao responsável pela rede.

## 6. Promoção de individual para rede

1. Confirmar administrador.
2. Verificar integridade.
3. Criar backup completo.
4. Habilitar serviço e identidade do principal.
5. Preservar todos os IDs e dados.
6. Testar operação local.
7. Liberar pareamento.

Falha em qualquer etapa deve deixar a instalação anterior utilizável ou oferecer restauração.

## 7. Adição, remoção e substituição

Tela “Gerenciar computadores” permitirá:

- nomear Caixa, Recepção, Estoque etc.;
- ver última conexão e versão;
- adicionar e revogar estação;
- renovar pareamento;
- bloquear dispositivo perdido;
- verificar compatibilidade.

Substituir o computador principal é outro fluxo: backup validado, instalação principal limpa, restauração e reemissão de credenciais. Não será tratado como simples adição de estação.

## 8. Reinstalação e dados

| Ação | Comportamento obrigatório |
| --- | --- |
| Reparar | Preservar banco, XMLs, anexos e backups. |
| Reinstalar aplicativo | Preservar dados e revalidar versão. |
| Atualizar | Criar backup, migrar e validar. |
| Reconfigurar rede | Preservar dados e revogar apenas credenciais escolhidas. |
| Desinstalar estação | Remover app local; não tocar no servidor. |
| Desinstalar principal | Alertar, exigir backup e preservar dados por padrão. |
| Apagar dados | Fluxo separado, autenticação forte e confirmação inequívoca. |

## 9. Atualização

### Pré-condições

- pacote autêntico e íntegro;
- versão de origem suportada;
- espaço livre suficiente;
- backup concluído e verificável;
- ausência de transações em andamento.

### Ordem

1. Colocar servidor em modo de manutenção.
2. Encerrar novas gravações de estações.
3. Criar backup.
4. Instalar binários.
5. Executar migrações.
6. Executar verificação de saúde.
7. Liberar serviço.
8. Atualizar estações ou exigir versão compatível.

Não fazer atualização destrutiva silenciosa. Falha apresenta código de suporte e caminho seguro.

## 10. Diagnóstico

Mostrar sem revelar segredos:

- modo da instalação;
- versão do aplicativo, API e schema;
- serviço em execução;
- banco acessível;
- espaço livre;
- último backup e validação;
- estações e compatibilidade;
- rede local e descoberta;
- relógio e fuso;
- integridade básica de pastas;
- identificador de correlação dos erros recentes.

Um pacote de suporte poderá ser exportado com consentimento e revisão do conteúdo. XMLs, documentos, nomes, telefones e descrições de serviço não serão incluídos por padrão.

## 11. Limites comunicados

- estações dependem do principal ligado;
- internet não é necessária para operação local;
- acesso remoto deverá usar solução segura posterior, nunca abertura automática do roteador;
- energia estável e backup externo são recomendados;
- sistema operacional e hardware mínimos serão exibidos antes da compra e instalação.

