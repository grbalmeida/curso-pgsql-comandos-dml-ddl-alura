# Alterando informações

### Renomeando tabela

```sql
ALTER TABLE tabela RENAME TO tabela_renomeada;
```

### Renomeando colunas

```sql
ALTER TABLE tabela_renomeada RENAME coluna1 TO primeira_coluna;
ALTER TABLE tabela_renomeada RENAME coluna2 TO segunda_coluna;
```

### Adicionar coluna

```sql
ALTER TABLE tabela_renomeada ADD COLUMN terceira_coluna VARCHAR(255);
```