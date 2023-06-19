# Tipos

### Criação da tabela filme utilizando a constraint de CHECK para validar o campo classificacao

```sql
CREATE TEMPORARY TABLE filme (
	id SERIAL PRIMARY KEY,
	nome VARCHAR(255) NOT NULL,
	classificacao VARCHAR(255) CHECK (classificacao IN ('LIVRE', '12_ANOS', '14_ANOS', '16_ANOS', '18_ANOS'))
);
```

### Criação da tabela filme utilizando o campo ENUM

```sql
CREATE TYPE CLASSIFICACAO AS ENUM ('LIVRE', '12_ANOS', '14_ANOS', '16_ANOS', '18_ANOS');

CREATE TEMPORARY TABLE filme (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    classificacao CLASSIFICACAO
);
```