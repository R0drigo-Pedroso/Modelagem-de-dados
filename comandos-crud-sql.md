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