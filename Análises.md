# Análises do Negócio
***
### Com a sintaxe básica em SQL trouxe os 10 primeiros  orçamentos mais altos que a empresa realizou, contendo:
- valor do orçamento
- data da cotação
- cliente
- estado
***
```sql
SELECT valor_do_orcamento, 
       data_cotacao, 
       cliente, 
       estado
FROM forcamentos
ORDER BY valor_do_orcamento DESC
LIMIT 10
```
***
Atráves dessa análise
***
### Com a utilização das fórmulas estatísticas do SQL e com base nos status, foi criada colunas de:
- total orçado
- média orçado
- quantidade de orçamentos
- quantidade de clientes
***
```SQL
SELECT 
    status,
    SUM (valor_do_orcamento) AS total_orcado,
    AVG (valor_do_orcamento) AS media_orcado,
    COUNT (*) AS qtd_orcamentos,
    COUNT (DISTINCT cliente) AS qtd_clientes
FROM forcamentos
GROUP BY status
ORDER BY total_orcado DESC
```
***
Atráves dessa análise
***
### Com a utilização do SELECT DISTINCT trouxe o nome de todos os clientes da empresa SolutioX de forma distinta
***
```sql
SELECT DISTINCT status, cliente
FROM forcamentos
```
***

