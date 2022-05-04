# Comando SQL para CRUD - Referência

## Resumo

C - Create (inserir dados)

R - Read (ler dados)

U - Update (atualizar dados)

D - Delete (deletar dados)

<hr>

## INSERT
### FABRICANTES
```sql	
INSERT INTO fabricantes (nome) VALUES ('Asus');
INSERT INTO fabricantes (nome) VALUES ('Dell');
INSERT INTO fabricantes (nome) VALUES ('Apple'), ('LG'), ('Samsung'), ('Brastemp');
```	

### PRODUTOS
```sql
INSERT INTO produtos (nome, descricao, preco, quantidade, fabricantes_id) VALUES(
    'Ultrabook','Ultrabook Asus com processador Intel Core I12, memória RAM de 16GB e Windows 11', 6500.99, 7, 1); 
    );

    INSERT INTO produtos (nome, descricao, preco, quantidade, fabricantes_id) VALUES(
    'Tablet Android','Tablet com a versão 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64GB', 4999, 3, 5 # Samgung
    );

    INSERT INTO produtos (nome, descricao, preco, quantidade, fabricantes_id) VALUES(
        'Geladeira','Refrigerador Frost-free com acesso à Internet das coisas bla bla bla', 1500, 10, 6 # Brastemp
    ), (
        'Iphone 13 Pro Max', 'Alta durabilidade, processador Bionic 14, 128 GB de armazenamento, 6GB de RAM, câmera de 12MP e tela de 6,7 polegadas', 6999.99, 3, 3 # Apple
    ), (
        'Ipad Mini', 'Tela de 7 polegadas, processador A10, 64 GB de armazenamento, Wi-Fi e Bluetooth, acesso ao iCloud.', 4999.99, 8, 3 # Apple
    );
```
<hr>

## Exercício
- Insira mais 2 fabricantes: Positivo e Microsoft

- Insira mais 2 produtos: 
        - Xbox, console de ultima geração com acesso ao melhores jogos, 2999.99, 6, microsoft

        - Ultabook, Equipamento processador AMD Ryzen 5 de RAM, placa de vídeo AMD Radeon RX 580, 4GB de memória RAM, tela de 10 polegadas, Windows 10, preço de 4999.99, 7, positivo;


### FABRICANTES
```sql
    INSERT INTO fabricantes (nome) VALUES ('Microsoft'), ('Positivo');
```

### PRODUTOS
```sql
    INSERT INTO produtos (nome, descricao, preco, quantidade, fabricantes_id) VALUES(
            'Xbox','Console de ultima geração com acesso ao melhores jogos', 2999.99, 6, 7
        ),
        (
            'Ultabook', 'Equipamento processador AMD Ryzen 5 de RAM, placa de vídeo AMD Radeon RX 580, 4GB de memória RAM, tela de 10 polegadas, Windows 10', 4999.99, 7,8
        ); 
```
<hr>

## SELECT

### Ler dados da tabela produtos
```sql
SELECT * FROM produtos;
SELECT nome, preco FROM produtos;
SELECT nome, preco FROM produtos WHERE preco < 5000; 
SELECT nome, descricao FROM produtos WHERE fabricantes_id = 3;
```


### Operadores Lógicos: E OU NÃO
```sql
SELECT * FROM produtos WHERE preco >= 5000 AND preco < 8000;

SELECT nome, preco FROM produtos WHERE fabricantes_id = 3 OR fabricantes_id = 7;
                                    --- dos Fabricantes apple ou microsoft

-- Monte uma consulta que traga nome, preco e quantidade de todos os produtos exceto os da fabricante apple

```

```sql	
SELECT nome, preco, quantidade FROM produtos 
WHERE fabricantes_id != 3; # Não é da fabricante apple

-- ! = NOT # Não é

-- IN = Não é operador logico
-- forma de usar --

-- SELECT nome, preco, quantidade FROM produtos
-- WHERE fabricantes_id NOT IN (3, 7);
```	
<hr>

### Filtros

```sql	
SELECT nome, preco FROM produtos ORDER BY preco; # Ordenação por preço menor para o maior  
SELECT nome, preco FROM produtos ORDER BY preco DESC; # Ordenação por preço decrescente - maior para o menor

SELECT nome, descricao FROM produtos WHERE descricao LIKE '%processador%'; # Busca por palavra chave
```
### Operações e Funções de agregação

```sql	
SELECT SUM(preco) FROM produtos; # Somar todos os preços - Geral

SELECT SUM(preco) AS TOTAL FROM produtos; # Somar todos os preços e nomenar como TOTAL (nome da coluna)

SELECT SUM(quantidade) AS "Quantidade em Estoque" FROM produtos; # Somar todas as quantidades e nomenar como "Quantidade em Estoque"

SELECT SUM(quantidade) AS "Quantidade em Estoque Apple" FROM produtos WHERE fabricantes_id = 3; # Somar todas as quantidades de produtos da fabricante apple e nomenar como "Quantidade em Estoque"

-- AVG (Avarage)
SELECT AVG(preco) AS "Média dos Preços" FROM produtos; # Média dos preços

SELECT ROUND(AVG(preco), 2) AS "Média dos Preços" FROM produtos; # Média dos preços com 2 casas decimais

-- COUNT (Contagem)
SELECT COUNT(id) AS "Quantidade de produtos" FROM produtos; # Quantidade de produtos

SELECT COUNT(fabricantes_id) AS "Quantidade de Fabricantes" FROM produtos;

-- DISTINCT é um comando para evitar a duplicidade na consulta de produtos
SELECT COUNT(DISTINCT fabricantes_id) AS "Quantidade de Fabricantes" FROM produtos;

SELECT nome, preco, quantidade, (preco * quantidade) AS "TOTAL" FROM produtos; # Total de cada produto
```	

### Agrupamento

```sql
SELECT fabricantes_id, SUM(preco) AS "Total" FROM produtos GROUP BY fabricantes_id; # Agrupa por fabricante

-- GRUP BY permite segmentaçã reaultado da consulta.
-- nese cassa, somamo todos os preços e segmentamos / agrupamento por cada fabricante`
```	
### Update (Sempre colocar WHERE)

```sql
UPDATE fabricantes SET nome = 'Microsoft Brasil' WHERE id = 7; # 
```	