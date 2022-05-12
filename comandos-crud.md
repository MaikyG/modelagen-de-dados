# Comandos CRUD SQL

## Resumo de sigla
- c -> CREATE (INSERT, inserir dados)
- R -> READ (SELECT, leitura de dados)
- U -> UPDATE (UPDATE,atualizar dados)
- D -> DELETE (DELETE,excluir dados)

## INSERT

### Fabricantes
INSERT INTO fabricantes(nome) VALUES('Asus');
INSERT INTO fabricantes(nome) VALUES('Dell');
INSERT INTO fabricantes(nome) VALUES('AMD');
INSERT INTO fabricantes(nome) VALUES('Intel');
INSERT INTO fabricantes(nome) VALUES('123');

INSERT INTO fabricantes(nome) VALUES('Gigabit'),('Asrock'),('MSI')

### Produtos
INSERT INTO produtos(nome,preco, quantidade, descricao, fabricante_id) VALUES('Placa mae', 600.99, 5, 'placa mae Asus', 1 )
INSERT INTO produtos(nome,preco, quantidade, descricao, fabricante_id) VALUES('Placa mae', 900.99, 2, 'placa mae MSI', 7 )

INSERT INTO produtos(nome,preco, quantidade, descricao, fabricante_id) VALUES('computador', 5000.00, 4, 'computador dell, com os negocio tudo ', 2 )

INSERT INTO produtos(nome,preco, quantidade, descricao, fabricante_id) VALUES
('placa de video', 3000.00, 2, 'placa de video de alto desempenho', 5 ),
('processador', 1550.00, 6, 'processador amd', 3 ),
('processador', 2000.00, 8, 'processador intel', 4 ),
('notebook', 8000.00, 3, 'notebook', 7 ),
('placa mae', 1000.00, 2, 'Placa mae', 6 )

 ## SELECT

 SELECT nome, preco FROM produtos;
 SELECT preco, nome FROM produtos;
 SELECT nome, preco FROM produtos WHERE preco < 3000 AND > 2000;
 SELECT nome, preco, fabricante FROM produtos WHERE nome = 'placa mae';

 SELECT nome, preco FROM produtos WHERE fabricante_id = 3 OR fabricante_id =4;

-- ORDER BY = clasifique por(ordem crescente...o padrão) ORDER BY nome DESC (ordem decrescente) 
 SELECT nome, preco, descricao FROM produtos ORDER BY nome 
 SELECT nome, preco, descricao FROM produtos ORDER BY preco

 SELECT
    fabricantes.nome AS Fabricante,
    produtos.nome AS Nome,
    produtos.preco AS Preço,
    produtos.descricao AS Descrição
FROM produtos INNER JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id ORDER BY preco

-- INNER JOIN: comando que permite juntar duas ou mais tabelas
-- ON: comando para indicar a maneira como as tabelas são juntadas
-- AS: comando que permite dar um apelido para as colunas

## UPDATE
UPDATE fabricantes SET nome = 'atualização' WHERE id = 8; -- SEMPRE USER WHERE, SEMPRE DE UMA CONDIÇÃO!!!

## DELETE
DELETE FROM fabricantes WHERE id = 8
