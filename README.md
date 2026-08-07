# repair-shop-management

Sistema de gestão offline-first para oficinas de automóveis, motocicletas e bicicletas.

## Documentação mestre

Status: planejamento inicial

Versão da documentação: 0.1

Data-base: 7 de agosto de 2026

## Propósito

Este pacote transforma as decisões iniciais do produto em uma base executável de planejamento. O objetivo é desenvolver um sistema desktop comercial para oficinas de automóveis, motocicletas e bicicletas, com operação local, licença permanente e possibilidade de uso em vários computadores da mesma rede.

O histórico técnico do veículo é o centro do produto. Ordens de serviço, peças, estoque, caixa, documentos fiscais e garantias devem formar uma única linha do tempo confiável.

## Decisões já tomadas

- Python será a linguagem principal.
- PySide6 será usado na interface desktop.
- O produto funcionará sem internet.
- A edição individual funcionará em um computador.
- A edição em rede usará um servidor local e estações na mesma rede.
- O cliente receberá um instalador único e guiado.
- O usuário não precisará instalar Python, banco de dados ou ferramentas de desenvolvimento.
- O XML de NF-e de fornecedores alimentará estoque e financeiro.
- O fluxo de caixa realizado e projetado fará parte da versão comercial.
- O custo médio ponderado móvel será o método padrão de valoração gerencial do estoque.
- A rotação física poderá priorizar itens mais antigos ou próximos do vencimento, independentemente do método de custo.
- Emissão fiscal não faz parte da primeira versão comercial.
- Reinstalação, reparo e atualização não poderão apagar dados silenciosamente.
- O nome “Livro Diário” será evitado; o recurso operacional será chamado de “Diário da Oficina” ou “Registro Diário”.

## Ordem de leitura

1. [Visão e escopo do produto](docs/01-VISAO-E-ESCOPO.md)
2. [Requisitos rastreáveis](docs/02-REQUISITOS.md)
3. [Domínio, dados e fluxos](docs/03-DOMINIO-E-FLUXOS.md)
4. [Arquitetura e decisões técnicas](docs/04-ARQUITETURA.md)
5. [Instalação, rede e atualização](docs/05-INSTALACAO-E-REDE.md)
6. [XML e documentos fiscais](docs/06-XML-FISCAL.md)
7. [Segurança, privacidade e recuperação](docs/07-SEGURANCA-E-RECUPERACAO.md)
8. [Qualidade e estratégia de testes](docs/08-QUALIDADE-E-TESTES.md)
9. [Roadmap até a versão comercial](docs/09-ROADMAP-COMERCIAL.md)
10. [Operação, suporte e modelo comercial](docs/10-OPERACAO-E-SUPORTE.md)
11. [Contexto para IA](AI_CONTEXT.md)

Documentos de governança:

- [Guia de contribuição](CONTRIBUTING.md)
- [Política de segurança](SECURITY.md)
- [Registros de decisão arquitetural](docs/adr/README.md)

## Fontes de verdade

Quando houver conflito entre documentos, prevalece a seguinte ordem:

1. Requisitos legais e fiscais aplicáveis no momento da entrega.
2. Requisitos aprovados em `docs/02-REQUISITOS.md`.
3. Decisões arquiteturais registradas em `docs/04-ARQUITETURA.md`.
4. Roadmap e escopo de versão em `docs/09-ROADMAP-COMERCIAL.md`.
5. Demais documentos e exemplos.

Qualquer mudança de regra deve atualizar os documentos afetados na mesma alteração de código.

## Público

- **Empreendedor:** visão, escopo, roadmap, riscos e critérios comerciais.
- **Usuário da oficina:** fluxos, instalação e comportamento esperado.
- **Desenvolvedor iniciante:** explicações de termos, limites de cada módulo e ordem de implementação.
- **Desenvolvedor experiente:** requisitos identificados, arquitetura, integridade, segurança e critérios de aceite.
- **IA de desenvolvimento:** decisões, invariantes, fontes de verdade e limites descritos em `AI_CONTEXT.md`.

## O que significa “comercialmente pronto”

Ter todas as telas não é suficiente. A versão 1.0 somente poderá ser vendida quando passar pelos critérios de liberação documentados no roadmap, incluindo instalador confiável, atualização com migração, backup restaurável, controle de acesso, auditoria, desempenho, documentação, suporte e piloto real.
