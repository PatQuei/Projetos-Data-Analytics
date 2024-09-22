
# Desafio de Projeto Power BI: Relatório de Vendas e Produtos

Este projeto foi desenvolvido como parte de um desafio, focando na criação de uma página de detalhes e na disposição estratégica de visuais para facilitar a compreensão e o consumo de dados por parte do cliente.

## Objetivos

- Criar uma página de detalhes conforme solicitado no desafio.
- Dispor os visuais de forma que o cliente possa consumir o conteúdo com clareza.
- Desenvolver as medidas necessárias para suportar as análises.

## Visuais Implementados

1. **TOP 3 Produtos**  
   Visual que destaca os três produtos mais vendidos ou lucrativos, auxiliando o cliente a identificar rapidamente os itens de maior sucesso.

2. **Principais Países em Vendas/Profit**  
   Apresentação dos países com maiores valores de vendas ou lucro (ou outro critério), permitindo uma visão geográfica da performance.

3. **Gráfico de Dispersão: Unidades Vendidas x Vendas por Mês**  
   Gráfico de dispersão mostrando a relação entre as unidades vendidas e o volume de vendas ao longo dos meses, destacando possíveis tendências.

4. **Agrupamentos de Dados**  
   Visuais que agrupam os dados por categorias relevantes (como produto, país ou período), facilitando análises segmentadas.

5. **Compartimentação dos Dados**  
   Apresentação que segmenta os dados em compartimentos específicos para permitir comparações diretas e análises detalhadas.


## Medidas Criadas

Para viabilizar as análises do relatório, as seguintes medidas foram desenvolvidas:

1. **Total de Vendidos**  
   `SUMX(financials, financials[Units Sold])`  
   Esta medida calcula o total de unidades vendidas, somando todas as vendas registradas.

2. **Máximo Sold**  
   `MAX(financials[Units Sold])`  
   Retorna o valor máximo de unidades vendidas em uma única transação.

3. **Meta de Vendas**  
   `[total sales] * 0.8`  
   Calcula uma meta de vendas correspondente a 80% das vendas totais, auxiliando no acompanhamento de metas de performance.

4. **Outliers de Vendas**  
   `CALCULATE([total de vendidos], FILTER(VALUES(financials[Product]), COUNTROWS(FILTER(financials, [total de vendidos] >= 150)) > 0))`  
   Filtra os produtos com um total de unidades vendidas maior ou igual a 150, identificando outliers nas vendas.

5. **Segmentos Agrupados**  
   `DISTINCT('financials'[Segmentos agrupados])`  
   Retorna os segmentos agrupados, facilitando o estudo de tendências e comportamentos por segmento.


## Imagem do Relatório

![Relatório - Página Inicial](link_para_o_print_da_pagina_inicial)

## Ferramentas Utilizadas

- **Power BI Desktop**: Para desenvolvimento dos visuais e das medidas.
- **DAX (Data Analysis Expressions)**: Para criação de cálculos personalizados e métricas.
  
## Conclusão

Este projeto demonstra como é possível criar um relatório eficiente em Power BI, priorizando a disposição dos visuais para facilitar a análise de dados pelo cliente.

