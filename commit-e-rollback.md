# COMMIT e ROLLBACK

### Comando que inicia uma transação, exclui cursos e volta atrás para não excluir os cursos

```sql
BEGIN;
DELETE FROM teste.cursos_programacao;
ROLLBACK;
```

### Comando que inicia uma transação, exclui cursos e commita (impossibilitando uso do rollback)

```sql
BEGIN;
DELETE FROM teste.cursos_programacao WHERE id_curso = 6;
COMMIT;
```