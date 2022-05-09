create database if not exists pizzaria;
use pizzaria;

CREATE TABLE Clientes (
 CodCliente INTEGER NOT NULL AUTO_INCREMENT,
 Nome VARCHAR(60),
 CPF VARCHAR(20) ,
 Telefone VARCHAR(20) ,
 email VARCHAR(250) ,
PRIMARY KEY(CodCliente));


CREATE TABLE Compras (
 CodCompra INTEGER NOT NULL AUTO_INCREMENT,
 Fornecedores_CodFornecedor INTEGER,
 Dt_Compra DATE ,
 Valor_Total FLOAT ,
 Desconto FLOAT ,
PRIMARY KEY(CodCompra));


CREATE TABLE Contas_Pagar (
 CodPagar INTEGER NOT NULL AUTO_INCREMENT,
 Fornecedores_CodFornecedor INTEGER,
 Descricao VARCHAR(120) ,
 Valor FLOAT ,
 dt_Vencimento DATE ,
 Dt_pagamento DATE ,
 Valor_Pago FLOAT ,
PRIMARY KEY(CodPagar));


CREATE TABLE Contas_Receber (
 CodReceber INTEGER NOT NULL AUTO_INCREMENT,
 Clientes_CodCliente INTEGER,
 Descricao VARCHAR(120) ,
 Valor FLOAT ,
 dt_Vencimento DATE ,
 Dt_Recebimento DATE ,
 Valor_Recebido FLOAT ,
PRIMARY KEY(CodReceber));


CREATE TABLE Entregas (
 CodEntrega INTEGER NOT NULL AUTO_INCREMENT,
 Dt_Entrega DATE ,
 Hora_Entrega TIME ,
 Quant_Pedidos INTEGER ,
 Troco FLOAT ,
 Entregador VARCHAR(60) ,
PRIMARY KEY(CodEntrega));


CREATE TABLE Estoque (
 CodMovimentacao INTEGER NOT NULL AUTO_INCREMENT,
 Produtos_CodProduto INTEGER,
 Descricao VARCHAR(120) ,
 Quantidade INTEGER ,
 Entrada_Saida CHAR(1) ,
 Observacao VARCHAR(255) ,
PRIMARY KEY(CodMovimentacao));


CREATE TABLE Forma_Pagamento (
 CodFormapagamento INTEGER NOT NULL AUTO_INCREMENT,
 Descricao VARCHAR(120) ,
 Juros FLOAT ,
 Desconto FLOAT ,
PRIMARY KEY(CodFormapagamento));


CREATE TABLE Fornecedores (
 CodFornecedor INTEGER NOT NULL AUTO_INCREMENT,
 Razao_Social VARCHAR(250) ,
 Nome_Fantasia VARCHAR(120) ,
 CNPJ VARCHAR(20) ,
 Endereco VARCHAR(250) ,
 Site VARCHAR(120) ,
 Email VARCHAR(120) ,
 Contato VARCHAR(60) ,
 Telefone VARCHAR(20) ,
PRIMARY KEY(CodFornecedor));


CREATE TABLE Itens_Compra (
 Produtos_CodProduto INTEGER NOT NULL ,
 Compras_CodCompra INTEGER NOT NULL ,
 Quantidade INTEGER ,
 Valor_Unitario FLOAT ,
PRIMARY KEY(Produtos_CodProduto, Compras_CodCompra));


CREATE TABLE Itens_Pedido (
 Pedidos_CodPedido INTEGER NOT NULL ,
 Produtos_CodProduto INTEGER NOT NULL ,
 Quantidade INTEGER ,
 Valor_Unitario FLOAT ,
PRIMARY KEY(Pedidos_CodPedido, Produtos_CodProduto));


