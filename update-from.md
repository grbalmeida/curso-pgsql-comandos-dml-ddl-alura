# UPDATE FROM

### Atualização do nome dos cursos de PHP, Java e C++

```sql
UPDATE academico.curso SET nome = 'PHP Básico' WHERE id = 4;
UPDATE academico.curso SET nome = 'Java Básico' WHERE id = 5;
UPDATE academico.curso SET nome = 'C++ Básico' WHERE id = 6;
```

### Atualização do nome dos cursos da tabela teste.cursos_programacao com base na tabela academico.curso

```sql
UPDATE teste.cursos_programacao
SET nome_curso = nome
FROM academico.curso
WHERE teste.cursos_programacao.id_curso = academico.curso.id
AND academico.curso.id < 10;
```