# TRABALHO_BANCO_DE_DADOS
De acordo com as instruções do professor Hélio do Instituto Federal do Paraná (IFPR), foram realizadas atividades que deveriam ser colocar em um repositório público no GitHub.

#29/08/2022


CREATE DATABASE projeto;
USE projeto;

CREATE TABLE produto (
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nome VARCHAR(255) NOT NULL, 
preço_venda DECIMAL(8, 2) NOT NULL,
preço_custo DECIMAL(8, 2) NOT NULL,
ativo CHAR(1) NOT NULL DEFAULT 'S' 
);

INSERT INTO produto(nome,preço_custo,preço_venda) VALUES ('1 KG DE ARROZ', 2.99, 3.99);
INSERT INTO produto(nome,preço_custo,preço_venda) VALUES ('1 KG DE AÇUCAR', 1.09, 1.99);
INSERT INTO produto(nome,preço_custo,preço_venda) VALUES ('LATA DE MILHO', 5.35, 6.70);

CREATE TABLE estado(
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nome VARCHAR(255) NOT NULL UNIQUE,
sigla CHAR(2) NOT NULL UNIQUE,
ativo CHAR(1) NOT NULL DEFAULT 'S'
);

INSERT INTO estado(nome,sigla) VALUES ('PARANÁ','PR');
INSERT INTO estado(nome,sigla) VALUES ('SÃO PAULO','SP');
INSERT INTO estado(nome,sigla) VALUES ('MATO GROSSO','MT');

CREATE TABLE cidade(
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
nome VARCHAR(255) NOT NULL,
estado_id INT NOT NULL,
ativo CHAR(1) NOT NULL DEFAULT 'S',
FOREIGN KEY (estado_id) REFERENCES estado (ID)
);

INSERT INTO cidade(nome,estado_id) VALUES ('PARANAVAÍ',1);
INSERT INTO cidade(nome,estado_id) VALUES ('MARINGÁ',2);
INSERT INTO cidade(nome,estado_id) VALUES ('LONDRINA',3);
