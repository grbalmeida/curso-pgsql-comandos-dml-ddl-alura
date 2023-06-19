# Transações

### Comando para iniciar uma transação

```sql
START TRANSACTION;
```

### Comando para iniciar uma transação e apagar todos os cursos

```sql
BEGIN;
DELETE FROM teste.cursos_programacao;
```