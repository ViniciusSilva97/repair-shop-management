# Visão e escopo do produto

## 1. Problema observado

Pequenas oficinas precisam organizar clientes, veículos, serviços, estoque e caixa, mas muitas não desejam ou não conseguem manter uma assinatura mensal. Parte desse público prefere adquirir um sistema desktop e contratar melhorias, suporte ou atualizações quando necessário.

Planilhas e cadernos apresentam limitações recorrentes:

- histórico fragmentado ou perdido;
- dificuldade para localizar serviços anteriores;
- estoque sem rastreabilidade;
- divergência entre peças utilizadas e caixa;
- falta de visibilidade sobre dinheiro disponível, valores a receber e compromissos futuros;
- ausência de registro de autorização ou recusa;
- dependência da memória do proprietário;
- backups inexistentes ou inadequados.

## 2. Proposta de valor

Oferecer uma memória técnica e operacional da oficina que continue funcionando sem internet, seja simples de instalar e possa crescer de um para vários computadores.

O diferencial central é a linha do tempo do veículo. O produto deve responder rapidamente:

- O que o cliente relatou?
- Qual diagnóstico foi realizado?
- Quais serviços foram autorizados, executados ou recusados?
- Quais peças foram utilizadas e de qual compra vieram?
- Quem realizou o serviço?
- Existe garantia ativa?
- Qual manutenção está pendente?
- Qual documento e movimentação financeira estão ligados ao atendimento?

## 3. Segmentos iniciais

O sistema terá um núcleo comum com perfis configuráveis:

1. oficina de automóveis;
2. oficina de motocicletas;
3. oficina de bicicletas, inclusive elétricas.

Não serão mantidos três produtos independentes. Campos, terminologia e recursos específicos serão ativados por perfil.

## 4. Princípios do produto

### 4.1 Offline-first

As funções operacionais não dependem da internet. Atualizações, suporte remoto e backup externo podem usá-la, mas não podem bloquear a atividade normal.

### 4.2 Simplicidade visível

A complexidade técnica deve permanecer no instalador e nos serviços internos. O usuário não configurará Python, banco, API, IP fixo ou terminal.

### 4.3 Histórico confiável

Ordens finalizadas não serão reescritas silenciosamente. Correções relevantes gerarão auditoria com autor, data, valor anterior, valor novo e motivo.

### 4.4 Dados pertencem ao estabelecimento

O cliente poderá exportar dados e documentos em formatos comuns. A licença não poderá transformar os dados do usuário em reféns do fornecedor.

### 4.5 Crescimento sem reconstrução

Uma instalação individual poderá ser promovida a servidor da rede sem perder dados. A arquitetura separará regras de negócio, interface e persistência.

### 4.6 Segurança proporcional

O sistema tratará XMLs, anexos, credenciais e dados pessoais como entradas não confiáveis. Privilégios serão mínimos, operações críticas serão auditadas e backups serão verificáveis.

## 5. Escopo da versão comercial 1.0

A primeira versão comercial incluirá:

- empresa e preferências;
- usuários, funções e permissões;
- clientes;
- veículos por perfil;
- linha do tempo técnica;
- orçamento e ordem de serviço;
- inspeção, fotos e anexos;
- autorizações e recusas;
- peças, serviços, fornecedores e estoque;
- movimentações e inventário;
- caixa operacional e contas básicas;
- fluxo de caixa realizado e projetado em linguagem gerencial;
- custo médio ponderado móvel do estoque;
- importação de NF-e de fornecedor por XML;
- relatórios e documentos em PDF;
- backup, restauração e auditoria;
- instalador único;
- modo individual e modo em rede local;
- reparo, reconfiguração e atualização segura;
- diagnóstico para suporte.

## 6. Fora do escopo da versão 1.0

- contabilidade formal e escrituração do Livro Diário;
- folha de pagamento;
- SPED e obrigações acessórias completas;
- apuração tributária;
- emissão nativa de NF-e, NFC-e ou NFS-e;
- conciliação bancária automática;
- marketplace de peças;
- aplicativo móvel completo;
- sincronização offline entre vários servidores;
- acesso remoto por exposição direta de portas do roteador;
- inteligência artificial tomando decisões mecânicas ou fiscais;
- telemetria obrigatória;
- suporte a múltiplas filiais no mesmo banco.

Esses itens podem aparecer após a versão 1.0 mediante validação comercial e técnica.

## 7. Hipótese de modelo comercial

- licença permanente por estabelecimento e edição;
- quantidade de estações conforme licença;
- atualizações maiores opcionais e pagas;
- correções críticas conforme política publicada;
- suporte, implantação, backup externo e treinamento opcionais;
- nenhuma perda de acesso aos dados por encerramento de um plano opcional.

O modelo será validado com entrevistas e pilotos antes do lançamento.

## 8. Personas principais

### Proprietário

Deseja visão do caixa, estoque, produtividade, garantias, histórico e segurança dos dados.

### Atendente

Precisa localizar cliente e veículo rapidamente, registrar reclamação, produzir orçamento e acompanhar a ordem.

### Mecânico ou técnico

Precisa consultar histórico, registrar diagnóstico, peças, serviços, evidências e conclusão sem excesso de burocracia.

### Caixa/administrativo

Precisa receber ordens concluídas, registrar pagamentos, importar compras e conferir movimentações.

### Suporte

Precisa diagnosticar instalação, rede, banco, backup e versão sem acessar dados além do necessário.

## 9. Métricas iniciais de sucesso

- localizar o histórico de um veículo em até três interações;
- abrir uma ordem reutilizando cliente e veículo existentes sem redigitação;
- importar uma NF-e de fornecedor e preparar a entrada de estoque em poucos minutos;
- recuperar um backup validado em procedimento documentado;
- adicionar uma estação sem configuração manual de banco;
- manter rastreabilidade entre ordem, peça, estoque e financeiro;
- concluir pilotos sem perda ou corrupção de dados.
