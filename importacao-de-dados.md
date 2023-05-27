# Importaçao de dados

### Criação do schema teste

```sql
CREATE SCHEMA teste;
```

### Criação da tabela cursos_programacao

```sql
CREATE TABLE teste.cursos_programacao (
    id_curso INTEGER PRIMARY KEY,
    nome_curso VARCHAR(255) NOT NULL
);
```

### Populando tabela teste.cursos_programacao com dados de academico.curso

```sql
INSERT INTO teste.cursos_programacao
SELECT
	academico.curso.id,
	academico.curso.nome
FROM academico.curso
WHERE categoria_id = 2;
```