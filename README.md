# Dashboard de Análise de Vendas para E-commerce (Projeto de Portfólio)

## 📄 Resumo do Projeto
Este projeto consiste em uma análise completa de um banco de dados de e-commerce simulado para o ano de 2025. O objetivo foi responder a 5 perguntas de negócio chave, utilizando SQL para a extração e preparação dos dados e o Power BI para a criação de um dashboard interativo de 3 páginas, destinado a apoiar a tomada de decisão das equipes de Vendas, Marketing e Produto.

## 🛠️ Ferramentas Utilizadas
* **Banco de Dados:** MySQL
* **Extração e Preparação:** SQL (MySQL Workbench)
* **Visualização:** Power BI

---

## 📈 Análises Realizadas (As 5 Tarefas)
Foram desenvolvidas 5 consultas SQL para extrair os seguintes insights:

1.  **KPIs Gerais:** Cálculo do faturamento total, número de pedidos e total de clientes ativos.
2.  **Ranking de Popularidade:** Identificação dos TOP 5 produtos mais vendidos por frequência.
3.  **Análise Geográfica:** Mapeamento do faturamento e do número de clientes por cidade.
4.  **Oportunidades de Cross-sell:** Segmentação de produtos da categoria "Acessórios" com baixa performance de vendas.
5.  **Análise de Recência:** Identificação de clientes ativos no segundo semestre para campanhas de CRM.

---

## 📊 Dashboard Final no Power BI
O resultado de todas as análises foi consolidado em um dashboard de 3 páginas no Power BI.

### Página 1: Resumo Gerencial
Visão macro dos principais indicadores de performance do negócio.


![pagina1](https://github.com/user-attachments/assets/f5b878f6-57a1-4b11-aa64-9b800f9ac185)



### Página 2: Análise de Produtos
Visão detalhada sobre os produtos campeões de venda e as oportunidades de melhoria.


![pagina2](https://github.com/user-attachments/assets/7bd5f080-af2a-489b-a0a3-8d1f699aeaf2)



### Página 3: Análise de Clientes e Geografia
Visão sobre o perfil e a localização dos clientes, identificando os principais mercados e os clientes mais recentes.



![pagina3](https://github.com/user-attachments/assets/789645ff-c802-4d66-b5f4-2c5738415fe3)


---

## 👨‍💻 Scripts SQL

### Tarefa 1: KPIs Gerais do Negócio
-- A consulta mostra o faturamento total, o número de pedidos e a quantidade de clientes que fizeram alguma compra em 2025.
```sql
SELECT
    SUM(pro.preco * pe.quantidade) AS faturamento_total,
    COUNT(pe.id_pedido) AS total_pedidos,
    COUNT(DISTINCT c.id_cliente) AS clientes_que_compraram_algo
FROM
    Clientes AS c
INNER JOIN
    Pedidos AS pe ON c.id_cliente = pe.id_cliente
INNER JOIN
    Produtos AS pro ON pe.id_produto = pro.id_produto
WHERE
    pe.data_pedido BETWEEN '2025-01-01' AND '2025-12-31';
     


## 💡 Principais Insights Gerados
* A análise geográfica revelou que a cidade de São Paulo é o principal mercado, concentrando a maior parte do faturamento e dos clientes.
* Foi identificado que os produtos mais populares em frequência de vendas (ex: 'Teclado Mecânico') não são necessariamente os de maior faturamento ('Notebook Gamer'), sugerindo estratégias diferentes para cada um.
* Uma lista de clientes de alto potencial para campanhas de fidelização e reativação foi gerada com base em critérios de frequência e recência de compra.
