# Sequências

### Criação da tabela temporária auto

```sql
CREATE TEMPORARY TABLE auto (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(30) NOT NULL
);
```

### Comando para popular tabela auto

```sql
INSERT INTO auto (nome) VALUES ('Vinicius Dias');
```

### Comando para popular tabela auto informando o id

```sql
INSERT INTO auto (id, nome) VALUES (2, 'Vinicius Dias');
```

### Ao tentar inserir um novo registro sem informar o id ocorre um erro

```sql
INSERT INTO auto (nome) VALUES ('Outro nome');
-- ERROR:  duplicate key value violates unique constraint "auto_pkey" DETAIL:  Key (id)=(2) already exists.
```

### Criação de uma sequência própria

```sql
CREATE SEQUENCE eu_criei;
```

### Comando para obter o valor atual de uma sequência

```sql
SELECT CURRVAL('eu_criei');
```

### Comando para obter o próximo valor de uma sequência

```sql
SELECT NEXTVAL('eu_criei');
```

### Criação de uma tabela temporária que usa uma sequência como id

```sql
CREATE TEMPORARY TABLE auto (
    id INTEGER PRIMARY KEY DEFAULT NEXTVAL('eu_criei'),
    nome VARCHAR(30) NOT NULL
);
```