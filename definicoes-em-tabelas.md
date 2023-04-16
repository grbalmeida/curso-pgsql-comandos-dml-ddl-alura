# Definições em tabelas

### IF NOT EXISTS

Cria tabela apenas se não existir

```sql
CREATE TABLE IF NOT EXISTS academico.aluno (
    id SERIAL PRIMARY KEY,
    primeiro_nome VARCHAR(255) NOT NULL,
    ultimo_nome VARCHAR(255) NOT NULL,
    data_nascimento DATE NOT NULL
);
```

### DEFAULT

Cria uma tabela temporário com um valor default para as colunas primeiro_nome e data_nascimento

```sql
CREATE TEMPORARY TABLE aluno_tmp (
    id SERIAL PRIMARY KEY,
    primeiro_nome VARCHAR(255) NOT NULL DEFAULT 'Vinicius',
    ultimo_nome VARCHAR(255) NOT NULL,
    data_nascimento DATE NOT NULL DEFAULT NOW()::DATE
);
```

Ao inserir um registro com comando abaixo:

```sql
INSERT INTO aluno_tmp (ultimo_nome) VALUES ('Dias');
```

E pesquisar todos os dados:

```sql
SELECT * FROM aluno_tmp;
```

É exibido o resultado abaixo:

| id | primeiro_nome | ultimo_nome | data_nascimento |
| -- | ------------- | ----------- | --------------- |
| 1	 | Vinicius      | Dias        | 2023-04-15      |

### CHECK

Constraint que impede que o valor da coluna seja uma string vazia.

```sql
CREATE TEMPORARY TABLE tabela (
    coluna VARCHAR(255) NOT NULL CHECK(coluna <> '')
);
```

Ao tentar inserir uma string vazia, gera erro.

```sql
INSERT INTO tabela VALUES ('');
```

### UNIQUE

Restrição de UNIQUE para 2 colunas, não pode repetir o mesmo valor para as 2 colunas em outra linha

```sql
CREATE TEMPORARY TABLE tabela (
    coluna1 VARCHAR(255) NOT NULL,
    coluna2 VARCHAR(255) NOT NULL,
    UNIQUE (coluna1, coluna2)
);
```

```sql
INSERT INTO tabela VALUES ('Vinicius', 'Dias');  -- OK
INSERT INTO tabela VALUES ('Vinicius', 'Alves'); -- OK
INSERT INTO tabela VALUES ('Vinicius', 'Dias');
-- ERROR:  duplicate key value violates unique constraint "tabela_coluna1_coluna2_key"
```