# Comandos SQL - Referências

## Modelagem de dados Física

### Criar banco de dados


```sql
CREATE DATABASE vendas CHARACTER SET utf8mb4;
```

### Criar tabela Fabricantes

```sql
CREATE TABLE fabricantes (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
);
```

### Visualizar detalhes estruturais Fabricantes

```sql
    DESC fabricantes;
```	

### Criar tabela produtos

```sql
CREATE TABLE produtos (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(1000) NOT NULL,
    preco DECIMAL(6,2) NOT NULL,
    fabricante_id INT NOT NULL
);
```

### Adicioar campo/coluna em uma tabela 
```sql
    ALTER TABLE produtos ADD fabricantes_id INT NOT NULL AFTER preco;
```

### Visualizar detalhes estruturais produtos

```sql
    DESC produtos;
```

### Criação da chave estrageira (relacionamento entre tabelas)

```sql
ALTER TABLE produtos
    # CONSTRAINT é uma restrição definida no relacionamento entre tabelas
    ADD CONSTRAINT fk_produtos_fabricantes

    # A chave estrageira deve fazer Referência à chave primária
    FOREIGN KEY (fabricante_id) REFERENCES fabricantes(id);

```