# Dashboard de Análise de Vendas para E-commerce

## 📄 Resumo do Projeto
Este projeto tem como objetivo analisar um banco de dados de um e-commerce simulado, utilizando SQL para extrair e preparar os dados e o Power BI para criar visualizações e dashboards que gerem insights de negócio.

## 🛠️ Ferramentas Utilizadas
* **Banco de Dados:** MySQL
* **Extração e Preparação:** SQL (MySQL Workbench)
* **Visualização:** Power BI

---

## 📈 Análise 1: Performance Geográfica
A primeira análise busca entender a performance de vendas e o número de clientes por cidade, para identificar os principais mercados.

### Código SQL Utilizado
```sql
SELECT
    c.cidade,
    COUNT(DISTINCT c.id_cliente) AS numero_de_clientes_distintos,
    SUM(pro.preco * pe.quantidade) AS faturamento_total
FROM
    Clientes AS c
INNER JOIN
    Pedidos AS pe ON c.id_cliente = pe.id_cliente
INNER JOIN
    Produtos AS pro ON pe.id_produto = pro.id_produto
GROUP BY
    c.cidade
ORDER BY
    faturamento_total DESC;
```

### Principais Insights
* A consulta mostra o número de clientes e o faturamento total das vendas, agrupando nas cidades às quais os clientes pertencem.

---

## 📊 Visualização Final (Dashboard)
![github](https://github.com/user-attachments/assets/639784eb-1755-490f-a6e2-603f8cdbd0cd)
