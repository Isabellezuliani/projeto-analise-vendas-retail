# projeto-analise-vendas-retail
<img width="737" height="483" alt="Captura de tela 2026-09-25 220614" src="https://github.com/user-attachments/assets/094fa3ef-31d0-4320-b4f4-c4285d77fee0" />
<img width="392" height="334" alt="Captura de tela 2026-09-25 215714" src="https://github.com/user-attachments/assets/e8c91df6-0e75-403d-9ff2-feef63467477" />
<img width="548" height="392" alt="Captura de tela 2026-09-25 215654" src="https://github.com/user-attachments/assets/e4ae09de-2c6e-4a1b-ab6c-a4b36f86f794" />
<img width="662" height="276" alt="Captura de tela 2026-09-25 215643" src="https://github.com/user-attachments/assets/16e42814-30e4-4e7f-ae39-7379543c3632" />



Visão Geral do Projeto
Este projeto consiste em uma análise exploratória de dados de vendas no varejo para identificar padrões de compras, faturamento por categoria e perfil demográfico de clientes.

Tecnologias e Ferramentas Utilizadas
Power BI: Construção de dashboards, modelagem de dados e visualização.
Power Query: Limpeza e transformação de dados (ajuste de tipos e tratamento).
DAX: Criação de medidas calculadas (Faturamento Total, Total de Vendas e Ticket Médio).
Excel / CSV: Fonte de dados bruta.

---

Principais Métricas e Insights
- Faturamento Total: Métricas gerais consolidadas por período.
- Categorias Mais Lucrativas: Análise do volume de vendas agrupado por categoria de produto.
- Perfil dos Clientes: Distribuição de vendas por gênero e faixa etária.

*Consultas SQL (Análise Exploratória)

```sql
-- Total de Faturamento e Unidades Vendidas por Categoria
SELECT 
    `Product Category`, 
    SUM(Quantity) AS Total_Unidades, 
    SUM(`Total Amount`) AS Faturamento_Total
FROM retail_sales
GROUP BY `Product Category`
ORDER BY Faturamento_Total DESC;

-- Idade Média dos Clientes por Gênero
SELECT 
    Gender, 
    ROUND(AVG(Age), 1) AS Idade_Media
FROM retail_sales
GROUP BY Gender;
