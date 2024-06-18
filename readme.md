-- Criar banco de dados
CREATE DATABASE pizzaria_java_delights
DEFAULT COLLATE utf8_general_ci
DEFAULT CHARACTER SET utf8;

-- Usar o banco de dados
USE pizzaria_java_delights;

-- Criar tabela de clientes
CREATE TABLE clientes_tb (
    cliente_id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    endereco VARCHAR(255) NOT NULL,
    telefone VARCHAR(30) NOT NULL,
    cpf VARCHAR(11) NOT NULL UNIQUE, 
    email VARCHAR(255) NOT NULL UNIQUE
);

-- Criar tabela de pedidos
CREATE TABLE pedidos_tb (
    pedido_id INT AUTO_INCREMENT PRIMARY KEY,
    cliente_id INT,
    endereco VARCHAR(255) NOT NULL,
    sabor varchar(255) not null;
    valor DECIMAL(10, 2),
    data_pedido DATE,
    quantidade int(11),
    FOREIGN KEY (cliente_id) REFERENCES clientes_tb(cliente_id)
);