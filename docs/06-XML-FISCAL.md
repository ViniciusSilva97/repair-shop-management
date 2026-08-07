# XML e documentos fiscais

## 1. Limite da versão 1.0

A versão 1.0 importa e organiza documentos fiscais existentes. Ela não emite, autoriza, cancela, manifesta ou escritura documentos perante o Fisco.

Prioridade:

1. NF-e de entrada emitida por fornecedor de peças e materiais.
2. Eventos de cancelamento associados.
3. Vinculação de NF-e/NFC-e de saída já emitida.
4. Vinculação de NFS-e já emitida.
5. Integrações de emissão somente após a 1.0 e revisão fiscal especializada.

## 2. Casos de uso

### Importar compra

- selecionar XML único ou lote;
- validar e detectar duplicidade;
- reconhecer fornecedor;
- mapear produtos e conversões;
- revisar custos e quantidades;
- confirmar entrada;
- criar conta a pagar opcional.

### Consultar documento

- pesquisar por chave, número, emitente, destinatário, data e valor;
- abrir resumo e XML original conforme permissão;
- visualizar vínculos com estoque, financeiro e ordem;
- exibir situação e eventos conhecidos.

### Vincular documento a ordem

Permitir associação manual ou assistida. O XML normalmente não identifica inequivocamente o veículo; heurísticas nunca confirmarão o vínculo sozinhas.

## 3. Dados extraídos

- modelo, versão do leiaute e ambiente;
- chave de acesso, número e série;
- data de emissão e autorização disponíveis;
- emitente e destinatário;
- protocolo e código de situação disponíveis;
- itens, códigos, GTIN quando presente, descrições, NCM, CFOP, unidades e quantidades;
- valores unitários, totais, descontos, frete e outras despesas;
- tributos informados no XML;
- cobrança e duplicatas quando presentes;
- informações adicionais úteis sem tratá-las como comando.

O sistema não recalculará a validade tributária da nota na primeira versão. Ele exibirá dados recebidos e inconsistências técnicas detectáveis.

## 4. Segurança do parser

XML é entrada não confiável. O importador deverá:

- desabilitar entidades externas, DTD e resolução de rede;
- impor tamanho máximo de arquivo e lote;
- limitar profundidade, quantidade de nós e texto;
- usar biblioteca mantida e configuração segura;
- validar namespaces e versão suportada;
- não executar conteúdo embutido;
- usar diretório temporário controlado;
- sanitizar nomes e não confiar na extensão;
- registrar falha sem gravar conteúdo sensível no log;
- rejeitar arquivos compactados recursivamente ou fora da política.

## 5. Preservação e evidência

Para cada documento:

- guardar bytes originais recebidos;
- calcular SHA-256;
- registrar tamanho, data de importação, usuário e origem;
- guardar chave e versão;
- impedir alteração pelo fluxo comum;
- manter eventos vinculados, não sobrescrever o documento original;
- incluir original e metadados no backup.

## 6. Duplicidade e idempotência

Uma chave já conhecida deve apresentar o documento existente. Se os bytes forem diferentes:

- não substituir automaticamente;
- comparar hash, protocolo e situação;
- classificar como evento, versão recebida ou conflito para análise;
- impedir nova entrada de estoque;
- manter trilha de decisão.

Cada lote de importação possui ID. Repetir a confirmação após falha de rede não duplica movimentos.

## 7. Mapeamento de produtos

Ordem de sugestão:

1. vínculo previamente confirmado entre fornecedor e código do item;
2. GTIN válido, quando presente;
3. código interno conhecido;
4. correspondência assistida por descrição e unidade;
5. seleção ou cadastro manual.

Sugestão não é confirmação. O usuário revisa itens novos e ambíguos.

## 8. Conversões

Registrar de forma explícita:

```text
1 caixa fiscal = 12 unidades de estoque
2 caixas importadas = 24 unidades de entrada
```

A conversão é versionada por fornecedor/item. Alterar conversão futura não modifica importações anteriores.

## 9. Efeito no estoque e financeiro

Documento `validado` não significa `lançado`. Estados propostos:

- recebido;
- inválido;
- duplicado;
- aguardando mapeamento;
- pronto para lançamento;
- lançado;
- cancelado após lançamento;
- requer análise.

O cancelamento fiscal não deve apagar movimentos. Deve iniciar fluxo de estorno/reversão autorizado, considerando o que ocorreu fisicamente com a mercadoria.

## 10. NFS-e e evolução de leiautes

NFS-e segue domínio distinto de NF-e/NFC-e. O padrão nacional e regras de municípios continuam evoluindo. A arquitetura usará adaptadores por família e versão, com amostras de teste sem dados pessoais reais.

Campos de identificadores empresariais não devem ser limitados por suposição rígida incompatível com mudanças oficiais. Atualizações de IBS/CBS e demais leiautes serão tratadas como manutenção fiscal versionada.

## 11. Critérios de aceite do importador 1.0

- importar amostras autorizadas dos leiautes declarados;
- rejeitar XML truncado, excessivo ou com entidade externa;
- detectar duplicidade antes de movimentar estoque;
- preservar original e hash;
- mapear item com confirmação;
- converter unidade com cálculo decimal exato;
- fazer rollback completo se qualquer movimento falhar;
- emitir relatório de lote;
- restaurar XMLs e vínculos a partir do backup;
- provar por teste que NF-e de saída não baixa estoque duas vezes.

## 12. Referências oficiais

- [Esquemas XML de NF-e/NFC-e](https://www.nfe.fazenda.gov.br/portal/listaConteudo.aspx?tipoConteudo=BMPFMBoln3w%3D)
- [Portal da NFS-e — documentação técnica](https://www.gov.br/nfse/pt-br/biblioteca/documentacao-tecnica)
- [Atualizações e implantações da NFS-e](https://www.gov.br/nfse/pt-br/biblioteca/documentacao-tecnica/atualizacoes-e-implantacoes)
- [Serviço oficial de emissão de NFS-e padrão nacional](https://www.gov.br/pt-br/servicos/emitir-nota-fiscal-de-servico-eletronica)

As regras efetivas devem ser verificadas novamente na implementação e antes de cada liberação fiscal.

