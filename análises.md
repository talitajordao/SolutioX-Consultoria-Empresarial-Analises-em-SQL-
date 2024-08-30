# Análises do Negócio
***
### Com a sintaxe básica em SQL trouxe os 10 primeiros  orçamentos mais altos que a empresa realizou, contendo:
- valor do orçamento
- data da cotação
- cliente
- estado
- vendedor
***
```sql
SELECT valor_do_orcamento, 
       data_cotacao, 
       cliente, 
       estado,
       vendedor
FROM forcamentos
ORDER BY valor_do_orcamento DESC
LIMIT 10
```
***
Atráves dessa análise é possivel enxergar quais vendedores realizaram os maiores orçamentos para posteriormente analisar os fechamentos, assim pode-se mapear oque cada vendedor realizou para fechar com o cliente, com isso, visando o crescimento da empresa e desenvolvimento dos vendedores podem ser estrategicamente desenvolvidos atráves desses fechamentos.
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
Atráves dessa análise é possivel identificar os KPI'S do negócio. Analisar e gerenciar o nível do desempenho para alcançar e medir os objetivos e metas da empresa.
***
### Com a utilização do SELECT DISTINCT trouxe o nome de todos os clientes da empresa SolutioX de forma distinta
***
```sql
SELECT DISTINCT status, cliente
FROM forcamentos
```
***
Atráves dessa análise conseguimos entender quais são nossos clientes e é possivel criar estratégias para fidelizar ainda mais esses clientes e oferecer outros produtos e serviços, assim aumentando a receita da empresa.
***
### Com a utilização de WHERE e BETWEEN em SQL foi filtrado todos os orçamentos fechados (vendidos) no mês de Julho de 2020
***
```sql
SELECT 
    cliente,
    SUM(valor_do_orcamento) AS total_orcado
WHERE status = 'VENDIDO' AND data_cotacao BETWEEN '2020-07-01' AND '2020-07-31'
FROM forçamentos
GROUP BY cliente
ORDER BY total_orcado DESC
```
***

***
