# Detalhes do INSERT

Ao inserir um registro, aspas duplas são utilizadas para referenciar colunas e aspas simples para referenciar dados.

```sql
INSERT INTO tabela_renomeada
("primeira_coluna", "segunda_coluna", "terceira_coluna")
VALUES
('A', 'B', 'C');
```