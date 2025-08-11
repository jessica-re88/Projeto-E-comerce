# Projeto-E-comerce

Descrição 

Este projeto apresenta o modelo conceitual de um sistema de E-commerce, estruturado segundo o Modelo Entidade-Relacionamento (ER).
O objetivo é fornecer uma visão clara e abstrata das entidades, relacionamentos e restrições de negócio que compõem o sistema, servindo como base para o desenvolvimento lógico e físico do banco de dados.

O esquema foi projetado para atender operações essenciais de um comércio eletrônico, incluindo cadastro de produtos, vendas por fornecedores ou terceiros, gerenciamento de estoque, processamento de pedidos, controle de pagamentos e gestão de entregas.

Objetivos de Modelagem

O modelo busca:

    Representar clientes de forma genérica e especializada (Pessoa Física e Pessoa Jurídica), garantindo exclusividade (um cliente não pode ser PF e PJ ao mesmo tempo).

    Permitir que pedidos aceitem múltiplas formas de pagamento.

    Controlar estoque de produtos em diferentes locais.

    Registrar entregas com status e código de rastreio.

    Associar fornecedores e terceiros vendedores aos produtos vendidos.

    Manter a categoria do produto como atributo (quando não há necessidade de múltiplas categorias por produto).

Entidades e Principais Atributos
Cliente

    idCliente (PK)

    Nome

    Identificacao (CPF ou CNPJ, dependendo do tipo)

    Endereco

Especializações:

    Cliente_PF: Data de nascimento, CPF

    Cliente_PJ: Razão social, CNPJ

Produto

    idProduto (PK)

    Categoria (atributo)

    Descricao

    Valor

Pedido

    idPedido (PK)

    Status_Pedido

    Descricao

    Frete

    idCliente (FK)

Forma_Pagamento

    idFormaPagamento (PK)

    Tipo (Cartão, Pix, Boleto, etc.)

    Detalhes

Entrega

    idEntrega (PK)

    Status

    Codigo_Rastreio

    Data_Prevista

Fornecedor

    idFornecedor (PK)

    Razao_Social

    CNPJ

Terceiro_Vendedor

    idTerceiroVendedor (PK)

    Razao_Social

    Local

Estoque

    idEstoque (PK)

    Local

 Relacionamentos e Cardinalidades

    Cliente 1:N Pedido

    Pedido N:M Produto (com quantidade)

    Pedido N:M Forma_Pagamento

    Pedido 1:1 Entrega

    Produto N:M Estoque (com quantidade)

    Fornecedor N:M Produto

    Terceiro_Vendedor N:M Produto

Regras de Negócio

    Um cliente é exclusivamente Pessoa Física ou Pessoa Jurídica.

    Um pedido pode ter uma ou mais formas de pagamento.

    Uma entrega está associada a apenas um pedido.

    Estoque é controlado por produto e local.

    Categoria de produto é um atributo único no registro do produto.
