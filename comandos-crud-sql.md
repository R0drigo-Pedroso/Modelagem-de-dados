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