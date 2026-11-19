# Projeto TechStore
TechStore — Banco de Dados SQL
Repositório oficial de documentação e dos scripts SQL do Projeto Didático TechStore , desenvolvido na Unidade Curricular 12 ( Executar os Processos de Codificação, Manutenção e Documentação de Aplicativos Computacionais para Desktop ).

Informações da Equipe
Integrantes: Vitor Matheus Menezes de Araújo e Rafael Constantino
Turma: 14330
Identificação do Projeto
Nome do Projeto: TechStore ( techstore-banco-dados)
Objetivo do Sistema: Sistema de gerenciamento de banco de dados relacionado para uma loja de suprimentos de informática e eletrônicos, centralizando o controle de clientes, fornecedores, fornecedores, categorias, catálogo de produtos, estoque, pedidos, itens vendidos e pagamentos, além de Views e Stored Procedures para apoio à tomada de decisão.
Órfão Utilizado
MySQL 8.x (Sistema Gerenciador de Banco de Dados Relacional / MySQL Workbench)
SQL (DDL, DML, DQL, Views e Stored Procedures)
Git (Controle de versão local)
GitHub (Hospedagem e versionamento remoto)
Visual Studio Code (ambiente de edição e publicação Git)
Estrutura do Repositório
techstore-banco-dados/
├── README.md
├── docs/
│   ├── modelo-conceitual/
│   │   ├── modelo_conceitual.md
│   │   └── DER_conceitual.png
│   ├── modelo-logico/
│   │   └── modelo_logico.md
│   └── dicionario-de-dados/
│       └── dicionario_de_dados.md
├── banco/
│   ├── create_database.sql
│   ├── create_tables.sql
│   ├── inserts.sql
│   ├── consultas.sql
│   └── views_procedures.sql
└── imagens/
    └── DER.png
Estrutura do Banco de Dados
O banco de dados techstoreé estruturado em 8 tabelas relacionais :

CLIENTE: Armazena os dados cadastrais de pessoas físicas ou jurídicas que realizam compras ( id_cliente, nome, cpf_cnpj, email, telefone, data_cadastro).
VENDEDOR: Registrar os colaboradores responsáveis ​​por intermediário e registrar as vendas ( id_vendedor, nome, email, telefone, data_contratacao).
FORNECEDOR: Mantém o cadastro das empresas parceiras distribuidoras de produtos ( id_fornecedor, razao_social, nome_fantasia, cnpj, telefone, email).
CATEGORIA: Classifica e agrupa os produtos por segmento de informática ( id_categoria, nome_categoria, descricao).
PRODUTO: Controle o catálogo de itens comercializados, preços unitários, estoque e vínculos com categoria e fornecedor ( id_produto, nome_produto, descricao, preco_unitario, quantidade_estoque, id_categoria, id_fornecedor).
PEDIDO: Centraliza o histórico das transações de compras realizadas, conectando cliente e vendedor ( id_pedido, data_pedido, valor_total, status_pedido, id_cliente, id_vendedor).
ITEM_PEDIDO: Tabela associativa que resolve o relacionamento N:N entre PEDIDOe PRODUTO, detalhando detalhes e preço praticado na venda ( id_item_pedido, quantidade, preco_praticado, id_pedido, id_produto).
PAGAMENTO: Registra os contratos financeiros vinculados aos pedidos, forma de pagamento e status de processamento ( id_pagamento, data_pagamento, valor_pago, forma_pagamento, status_pagamento, id_pedido).
Ordem de Execução de Scripts SQL
banco/create_database.sql— Crie e selecione o banco de dados techstore.
banco/create_tables.sql— Crie 8 tabelas com chaves primárias, estrangeiras e restrições de integridade.
banco/inserts.sql— Insira a massa de dados inicial (5 categorias, 5 fornecedores, 10 clientes, 5 vendedores, 20 produtos, 30 pedidos, 62 itens de pedido e 30 pagamentos).
banco/consultas.sql— Executa filtros ( LIKE, BETWEEN, IN, IS NULL), junções ( INNER JOIN, LEFT JOIN), agregações ( GROUP BY, HAVING) e os 8 relatórios operacionais e gerenciais.
banco/views_procedures.sql— Cria as 5 Views e as 5 Stored Procedures da Etapa 4.