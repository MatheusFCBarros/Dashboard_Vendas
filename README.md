# Dashboard_Vendas
Dashboard criado a partir de dados de vendas de produtos 

Nesse projeto eu realizei etapas como:

## Conexão com fontes de dados

As base de dados utilizada estava dividida em 2 locais distintos. As informações de clientes e produtos estava salva em um banco de dados Postgree e as informações de vendas estavam salvas em uma API.

## ETL - Extrair, Transformar e Carregar dados

Após carregar os dados para o Power BI eu realizei a modelagem e trasnformação dos mesmos conforme a necessidade dos requisitos que eu teria que informar no Dashboard
Por fim o modelo ficou assim:

![Modelo](https://github.com/MatheusFCBarros/Dashboard_Vendas/blob/main/Modelo.png)

## Requisitos a serem respondidos

Eu respondi as seguintes questões:

Top 5 Clientes em compras

Top 5 Produtos vendidos

Total de vendas por Estado/Cidade - MAPA

Média de vendas por Estado/Cidade

## Criação de calculos com funções DAX

Vendas total = 
    SUMX(FACT_VENDAS, FACT_VENDAS[Quantidade] * FACT_VENDAS[Valor_uni])
    
Media cidade = 
    AVERAGEX(VALUES(DIM_LOCALIZACAO[Cidade]),[Vendas total])
    
Media estado = 
AVERAGEX(VALUES(DIM_LOCALIZACAO[Estado]),[Vendas total])

Quantidade produtos vendidos = 
IF(
    SUM(FACT_VENDAS[Quantidade])
    = BLANK()
    ,0
    ,SUM(FACT_VENDAS[Quantidade])
)

## Personalização do layout do relatório

![Dashboard](https://github.com/MatheusFCBarros/Dashboard_Vendas/blob/main/Dashboard.png)



Link para visualizar o Dashboard: bit.ly/3zzjROw
