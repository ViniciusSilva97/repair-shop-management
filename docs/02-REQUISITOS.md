# Requisitos rastreáveis

## 1. Convenções

- `RF`: requisito funcional.
- `RN`: regra de negócio.
- `RNF`: requisito não funcional.
- `AC`: critério de aceite.
- Prioridade `P0`: obrigatório para 1.0.
- Prioridade `P1`: importante, pode ser adiado mediante decisão explícita.
- Prioridade `P2`: evolução posterior.

Estados: proposto, aprovado, implementado, verificado ou adiado.

## 2. Empresa, usuários e acesso

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-EMP-001 | P0 | Cadastrar estabelecimento, nome, documento, contato, endereço e preferências. |
| RF-EMP-002 | P0 | Selecionar perfil automóvel, motocicleta, bicicleta ou misto. |
| RF-USR-001 | P0 | Cadastrar usuários individuais sem compartilhar senha. |
| RF-USR-002 | P0 | Definir funções e permissões por módulo e ação. |
| RF-USR-003 | P0 | Bloquear, desbloquear e encerrar sessões de usuários. |
| RF-USR-004 | P0 | Registrar autenticações e ações críticas. |
| RF-USR-005 | P1 | Exigir nova autenticação para operações sensíveis configuradas. |

## 3. Clientes e veículos

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-CLI-001 | P0 | Cadastrar pessoa física ou jurídica com dados mínimos configuráveis. |
| RF-CLI-002 | P0 | Pesquisar por nome, telefone, documento e dados do veículo. |
| RF-CLI-003 | P0 | Permitir mais de um veículo por cliente. |
| RF-CLI-004 | P0 | Inativar cliente sem apagar seu histórico. |
| RF-VEI-001 | P0 | Cadastrar veículo com campos comuns e específicos do perfil. |
| RF-VEI-002 | P0 | Identificar automóvel ou motocicleta por placa/chassi e bicicleta por número do quadro ou identificador interno. |
| RF-VEI-003 | P0 | Registrar quilometragem ou métrica equivalente em cada atendimento. |
| RF-VEI-004 | P0 | Transferir a titularidade operacional preservando histórico técnico e controlando dados pessoais anteriores. |
| RF-VEI-005 | P0 | Inativar veículo sem apagar ordens, documentos ou movimentações. |
| RF-VEI-006 | P1 | Registrar componentes de bicicleta elétrica, bateria e motor. |

## 4. Histórico do veículo

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-HIS-001 | P0 | Exibir linha do tempo cronológica por veículo. |
| RF-HIS-002 | P0 | Consolidar ordens, inspeções, diagnósticos, peças, documentos, garantias e recomendações. |
| RF-HIS-003 | P0 | Filtrar a linha do tempo por período e tipo de evento. |
| RF-HIS-004 | P0 | Destacar garantia ativa, recomendação pendente e problema recorrente. |
| RF-HIS-005 | P0 | Abrir o documento de origem de cada evento. |
| RF-HIS-006 | P1 | Comparar evolução de quilometragem e recorrência de serviços. |

## 5. Orçamento e ordem de serviço

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-OS-001 | P0 | Abrir ordem vinculada a cliente e veículo. |
| RF-OS-002 | P0 | Separar relato do cliente, inspeção, diagnóstico e solução executada. |
| RF-OS-003 | P0 | Registrar quilometragem, combustível, avarias e fotos de entrada. |
| RF-OS-004 | P0 | Adicionar serviços, peças, quantidades, preços, descontos e observações. |
| RF-OS-005 | P0 | Produzir orçamento antes da execução. |
| RF-OS-006 | P0 | Registrar autorização ou recusa por item, com data, usuário e evidência disponível. |
| RF-OS-007 | P0 | Controlar estados: rascunho, aguardando diagnóstico, aguardando autorização, autorizada, em execução, aguardando peça, concluída, entregue e cancelada. |
| RF-OS-008 | P0 | Designar técnico responsável e participantes. |
| RF-OS-009 | P0 | Registrar testes finais, garantia e recomendações. |
| RF-OS-010 | P0 | Gerar documento em PDF para orçamento, autorização e ordem concluída. |
| RF-OS-011 | P0 | Impedir alteração silenciosa de ordem finalizada. |
| RF-OS-012 | P1 | Capturar assinatura eletrônica simples ou confirmação por código. |
| RF-OS-013 | P1 | Registrar tempo de mão de obra sem vigilância invasiva. |

## 6. Catálogo, fornecedores e estoque

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-EST-001 | P0 | Cadastrar peças, produtos, serviços, unidades e categorias. |
| RF-EST-002 | P0 | Cadastrar fornecedores e referências de produtos por fornecedor. |
| RF-EST-003 | P0 | Registrar entrada, saída, reserva, devolução, perda e ajuste. |
| RF-EST-004 | P0 | Manter razão de estoque imutável e saldo calculável por movimentações. |
| RF-EST-005 | P0 | Vincular consumo de peça à ordem de serviço. |
| RF-EST-006 | P0 | Alertar estoque mínimo. |
| RF-EST-007 | P0 | Executar inventário e justificar diferenças. |
| RF-EST-008 | P0 | Registrar custo de aquisição e histórico de custo. |
| RF-EST-009 | P0 | Evitar saldo negativo conforme política configurada e permissão. |
| RF-EST-010 | P1 | Controlar localização física, lote e validade quando aplicável. |
| RF-EST-011 | P0 | Calcular o custo gerencial pelo custo médio ponderado móvel a cada entrada confirmada. |
| RF-EST-012 | P0 | Preservar quantidade, valor e custo médio anteriores em cada movimento para auditoria e reconstrução. |
| RF-EST-013 | P1 | Recomendar rotação física pelo item mais antigo ou pelo vencimento mais próximo quando houver lote/validade. |
| RF-EST-014 | P1 | Manter arquitetura preparada para PEPS como método opcional futuro, sem permitir troca retroativa silenciosa. |

## 7. Caixa e financeiro operacional

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-FIN-001 | P0 | Abrir e fechar caixa com usuário, horário e saldo informado. |
| RF-FIN-002 | P0 | Registrar recebimentos, pagamentos, sangrias, suprimentos, estornos e ajustes. |
| RF-FIN-003 | P0 | Vincular recebimento à ordem de serviço. |
| RF-FIN-004 | P0 | Registrar múltiplas formas e parcelas de pagamento. |
| RF-FIN-005 | P0 | Criar conta a pagar opcional a partir de compra importada. |
| RF-FIN-006 | P0 | Emitir relatório diário de caixa e divergências. |
| RF-FIN-007 | P0 | Exigir justificativa e auditoria para estorno ou ajuste. |
| RF-FIN-008 | P0 | Controlar contas a receber e a pagar com vencimento e situação. |
| RF-FIN-009 | P0 | Apresentar fluxo de caixa realizado por data efetiva de recebimento ou pagamento. |
| RF-FIN-010 | P0 | Apresentar fluxo de caixa projetado por vencimento, com períodos diário, semanal e mensal. |
| RF-FIN-011 | P0 | Converter previsão em realizado sem duplicar lançamento. |
| RF-FIN-012 | P0 | Exibir disponível atual, entradas, saídas, atrasos e saldo projetado em linguagem simples. |
| RF-FIN-013 | P1 | Permitir despesas e receitas recorrentes com geração controlada de previsões. |

O módulo é gerencial e não substitui escrituração contábil ou fiscal.

## 8. Documentos fiscais por XML

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-XML-001 | P0 | Importar um arquivo ou lote de XMLs de NF-e de fornecedor. |
| RF-XML-002 | P0 | Preservar XML original, chave de acesso, versão do leiaute e hash. |
| RF-XML-003 | P0 | Validar estrutura, limites, protocolo disponível e duplicidade. |
| RF-XML-004 | P0 | Extrair emitente, destinatário, itens, unidades, totais e dados fiscais informados. |
| RF-XML-005 | P0 | Vincular item fiscal a produto existente ou cadastrar novo após confirmação. |
| RF-XML-006 | P0 | Configurar conversão entre unidade fiscal e unidade de estoque. |
| RF-XML-007 | P0 | Preparar entrada de estoque para revisão antes de efetivar. |
| RF-XML-008 | P0 | Impedir que reimportação duplique estoque ou financeiro. |
| RF-XML-009 | P1 | Importar eventos de cancelamento e atualizar situação sem apagar histórico. |
| RF-XML-010 | P1 | Vincular NF-e de saída e NFS-e já emitidas à ordem, sem emitir documento. |

## 9. Anexos, relatórios e comunicação

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-ANX-001 | P0 | Anexar imagens e documentos com tamanho e tipos controlados. |
| RF-ANX-002 | P0 | Manter anexos organizados por entidade e incluídos no backup. |
| RF-REL-001 | P0 | Gerar PDFs de orçamento, ordem, recibo não fiscal e relatórios selecionados. |
| RF-REL-002 | P0 | Exportar tabelas autorizadas para CSV. |
| RF-REL-003 | P0 | Incluir identificação da empresa, versão e rastreabilidade nos documentos. |
| RF-COM-001 | P1 | Registrar que uma mensagem ou documento foi compartilhado, sem depender de integração externa. |

## 10. Instalação, rede, backup e atualização

| ID | Prioridade | Requisito |
| --- | --- | --- |
| RF-INS-001 | P0 | Fornecer um instalador único com modos individual, principal, estação e reparo. |
| RF-INS-002 | P0 | Instalar dependências e serviços sem ferramentas de desenvolvimento. |
| RF-INS-003 | P0 | Informar antes do modo em rede que todos os computadores devem estar na mesma rede local. |
| RF-INS-004 | P0 | Promover instalação individual a principal sem perder dados. |
| RF-INS-005 | P0 | Encontrar o servidor automaticamente e oferecer código de pareamento. |
| RF-INS-006 | P0 | Reinstalar ou reparar sem apagar banco e anexos. |
| RF-INS-007 | P0 | Separar exclusão de dados em fluxo administrativo explícito e protegido. |
| RF-BKP-001 | P0 | Criar backups consistentes, versionados e com retenção configurável. |
| RF-BKP-002 | P0 | Verificar integridade do backup e registrar resultado. |
| RF-BKP-003 | P0 | Restaurar por fluxo guiado com confirmação e backup preventivo. |
| RF-UPD-001 | P0 | Verificar autenticidade da atualização. |
| RF-UPD-002 | P0 | Criar backup e aplicar migrações antes de abrir a nova versão. |
| RF-UPD-003 | P0 | Impedir estação incompatível de executar operações destrutivas. |
| RF-DIA-001 | P0 | Exibir diagnóstico de rede, serviço, banco, versão, disco e backup. |

## 11. Regras de negócio essenciais

| ID | Regra |
| --- | --- |
| RN-001 | Um cliente pode ter vários veículos. |
| RN-002 | Um veículo possui um proprietário operacional atual, mas pode ter histórico de titularidade. |
| RN-003 | Uma ordem pertence a um único veículo e cliente no momento do atendimento. |
| RN-004 | Relato, diagnóstico e solução são informações distintas. |
| RN-005 | Apenas itens autorizados podem ser marcados como executados, salvo correção auditada. |
| RN-006 | Finalização de ordem e movimentos relacionados deve ser transacional. |
| RN-007 | Toda movimentação de estoque possui origem, autor, data e motivo. |
| RN-008 | Saldo não será corrigido por edição direta; será ajustado por nova movimentação. |
| RN-009 | Documento fiscal importado é identificado primariamente pela chave de acesso e contexto do emitente/destinatário. |
| RN-010 | XML importado não equivale automaticamente a lançamento confirmado. |
| RN-011 | Exclusão lógica preserva referências históricas. |
| RN-012 | Operação cancelada permanece auditável. |
| RN-013 | Ordem concluída deve gerar evento na linha do tempo. |
| RN-014 | Serviço recusado continua visível como recomendação pendente até resolução ou encerramento justificado. |
| RN-015 | O sistema não declara validade contábil ou fiscal além dos documentos oficiais importados. |
| RN-016 | O custo médio móvel somente é recalculado por entrada confirmada que afete valor e quantidade. |
| RN-017 | Saídas usam o custo médio vigente no instante da confirmação e não recalculam compras anteriores. |
| RN-018 | Rotação física por antiguidade/validade não altera, por si só, o método gerencial de valoração. |
| RN-019 | Uma previsão financeira liquidada torna-se realizada por vínculo, sem criar valor duplicado. |
| RN-020 | Mudança de método de custo após movimentações exige procedimento versionado, auditado e revisão profissional aplicável. |

## 12. Requisitos não funcionais

| ID | Categoria | Requisito/critério inicial |
| --- | --- | --- |
| RNF-DES-001 | Desempenho | Operações comuns devem responder em até 2 s no percentil 95 do cenário de referência. |
| RNF-DES-002 | Capacidade | Testar 20 mil veículos, 50 mil ordens, 10 mil produtos e 250 mil movimentações. |
| RNF-DES-003 | Concorrência | Validar pelo menos 10 estações simultâneas na edição em rede. |
| RNF-DIS-001 | Disponibilidade | A edição em rede funciona sem internet, mas exige servidor local ligado. |
| RNF-INT-001 | Integridade | Operações compostas críticas usam transações e idempotência. |
| RNF-SEG-001 | Segurança | Segredos não ficam em texto puro em arquivos acessíveis ao usuário comum. |
| RNF-SEG-002 | Segurança | Interfaces de rede aceitam somente origens e ações necessárias. |
| RNF-SEG-003 | Segurança | Atualizações e instaladores comerciais serão assinados. |
| RNF-PRI-001 | Privacidade | Coletar apenas dados necessários e oferecer exportação e procedimentos de atendimento a direitos. |
| RNF-USA-001 | Usabilidade | Fluxos principais operam sem terminal, IP manual ou conhecimento de banco. |
| RNF-ACE-001 | Acessibilidade | Navegação por teclado, foco visível, contraste e escalabilidade de fonte serão testados. |
| RNF-OBS-001 | Observabilidade | Logs técnicos serão estruturados, rotacionados e sem exposição indevida de dados. |
| RNF-MAN-001 | Manutenibilidade | Camadas de domínio não dependem diretamente de PySide6 ou mecanismo específico de banco. |
| RNF-COM-001 | Compatibilidade | Requisitos mínimos de Windows e hardware serão definidos após piloto; arquitetura inicial é x64. |
| RNF-REC-001 | Recuperação | Meta inicial de RPO de um dia útil e RTO assistido de até duas horas, validada em piloto. |

## 13. Critérios globais de aceite da versão 1.0

- nenhum defeito crítico aberto;
- restauração testada em máquina limpa;
- migração testada a partir de todas as versões públicas suportadas;
- instalador e atualização assinados;
- cenários de perda de energia e interrupção avaliados;
- permissões e auditoria verificadas;
- importador XML testado contra leiautes suportados e entradas maliciosas;
- testes de concorrência e desempenho aprovados;
- piloto em oficinas reais concluído;
- documentação de instalação, usuário, suporte e privacidade publicada;
- contrato, licença, política de suporte e responsabilidades revisados profissionalmente.
