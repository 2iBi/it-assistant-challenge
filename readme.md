[AdventureWorks sample databases](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms) é um conjunto de base de dados fornecidas pela Microsoft.

# Desafio
Usando a base de dados simplificada do [AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorksLT2019.bak), Resolva o desafio a seguir com o SQL Server:

## Parte 1 – Exercícios de SQL Server (10)

Exercício 1: Identificar os 5 produtos com maior margem de lucro unitária. Para cada produto, calcule a diferença entre o preço de venda (ListPrice) e o custo padrão (StandardCost). Liste os 5 com maior margem.

Exercício 2: Análise do ticket médio por cliente. Calcule o valor médio das encomendas realizadas por cada cliente.

Exercício 3: Produtos com vendas em queda (comparação anual). Compare o total vendido de cada produto entre dois anos consecutivos (por exemplo, 2013 e 2014) e liste os que tiveram queda.

Exercício 4: Clientes com crescimento no volume de compras. Mostre os clientes cujo total de compras em 2014 foi superior ao de 2013.

Exercício 5: Identificar produtos não vendidos. Liste os produtos que nunca foram vendidos (não existem em SalesOrderDetail).

Exercício 6: Encomendas entregues com atraso. Liste encomendas cujo envio (ShipDate) foi feito mais de 3 dias após a data da encomenda (OrderDate).

Exercício 7: Produtos mais vendidos por categoria. Liste, por cada categoria de produto, o produto mais vendido (em quantidade).

Exercício 8: Clientes que não compram há mais de um ano. Liste clientes cuja última compra foi há mais de 365 dias.

Exercício 9: Cálculo do tempo médio entre encomenda e envio. Determine, para cada cliente, o tempo médio entre OrderDate e ShipDate.

Exercício 10: Total de vendas por localização geográfica. Apresente o total de vendas agregadas por cidade e país dos clientes.

## Parte 2 – Relatórios com Crystal Reports (5)
Para estes exercícios, será necessário usar o Crystal Reports Developer Edition. Conta Trial Gratuita (30 dias). Para usar Crystal Reports, crie uma conta gratuita e descarregue a versão trial: [Download oficial – Crystal Reports Trial (SAP)](https://www.sap.com/products/technology-platform/crystal-reports.html)

#### Exercício 1: Relatório de Facturação por Cliente com Totais

Objectivo: Criar um relatório que liste os clientes e os seus respectivos pedidos, com totais por cliente e um total geral.

Instruções:
•	Usar as tabelas: SalesLT.Customer, SalesLT.SalesOrderHeader, SalesLT.SalesOrderDetail.

•	Mostrar:Nome do cliente, Número do pedido, Data do pedido, Produto (nome), Quantidade, Preço unitário e Total da linha (OrderQty * UnitPrice)

•	Agrupar por cliente.

•	Calcular o total por cliente e o total geral no final.

•	Dica: Utilize fórmulas para calcular o total por linha.


#### Exercício 2: Relatório de Produtos com Ruptura de Stock

Objectivo: Listar os produtos cujo stock disponível (Quantity) está abaixo do limite mínimo de segurança (definido por parâmetro).

Instruções:

•	Usar as tabelas: SalesLT.Product, SalesLT.ProductInventory.

•	Adicionar um parâmetro chamado @MinimoSeguranca para filtrar os produtos com stock abaixo do valor indicado.

•	Mostrar:Nome do produto, Localização (LocationID) e Quantidade em stock

•	Filtro: Quantity < @MinimoSeguranca


#### Exercício 3: Análise de Vendas por Região e Ano

Objectivo: Gerar um relatório com as vendas totais por região e por ano.

Instruções:

•	Usar as tabelas: SalesLT.Address, SalesLT.CustomerAddress, SalesLT.Customer, SalesLT.SalesOrderHeader.

•	Agrupar por: Estado/Região (StateProvince) e pelo Ano da data do pedido (OrderDate)

•	Mostrar:Ano, Nome do cliente, Número do pedido e Total do pedido

•	Calcular total por ano e por região.



#### Exercício 4: Relatório de Encomendas Atrasadas

Objectivo: Apresentar uma lista de encomendas cuja data de envio foi posterior à data estimada de envio.

Instruções:

•	Usar: SalesLT.SalesOrderHeader

•	Mostrar:Número da encomenda, Data da encomenda, Data estimada de envio (DueDate) e Data real de envio (ShipDate)

•	Adicionar fórmula para calcular o atraso: Datediff("d", DueDate, ShipDate)

•	Filtro: Encomendas onde ShipDate > DueDate

•	Ordenar por maior atraso.



#### Exercício 5: Sub-relatório de Itens por Encomenda

Objectivo: Criar um relatório principal com encomendas e um sub-relatório com os produtos de cada encomenda.

Instruções:

•	Relatório principal:

o	Usar: SalesLT.SalesOrderHeader

o	Mostrar: SalesOrderID, OrderDate, TotalDue

•	Sub-relatório:

o	Usar: SalesLT.SalesOrderDetail, SalesLT.Product

o	Mostrar: Nome do produto, quantidade, preço, total da linha

•	Ligar os relatórios através de SalesOrderID.

•	Incluir o sub-relatório dentro da secção de detalhes ou footer do grupo.



# Como entregar
Você deve gerar ficheiros em formato SQL para cada uma das consultas a serem criadas.
Assim que finalizar, nos avise pelo e-mail devchallenge@2iBi.com com:
- Titulo: **[Assistente Técnico de Primavera júnior] Teu nome**
- Link ou ficheiros sql do desafio anexado
- Informações sobre ti: Github, Linkedin entre outras informações que consideras importantes
