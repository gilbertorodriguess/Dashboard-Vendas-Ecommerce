# Dashboard-Vendas-Ecommerce
Projeto de análise de dados de um e-commerce usando SQL (MySQL) para extração de dados e Power BI para visualização.
select
	c.cidade,
    	count(distinct c.id_cliente)as numero_de_clientes_destintos,
    	sum(pro.preco * pe.quantidade) as faturamento_total
from Clientes as c
inner join Pedidos as pe on c.id_cliente = pe.id_cliente
inner join Produtos as pro on pe.id_produto = pro.id_produto
group by
	c.cidade
order by 
	faturamento_total desc;

-- A consulta mostra a o numero de clientes e o faturamento total das vendas, agrupando nas cidades ao quais os clientes pertencem--
