# DIO Bootcamp Data Analytics com Power BI

# Projeto de Modelagem e Transformação de Dados com DAX no Power BI

## Descrição do Projeto

Utilizaremos a tabela única de Financial Sample para criar as tabelas dimensão e fato do nosso modelo baseado em star schema.
O processo consiste na criação das tabelas com base na tabela original. A partir da cópia serão selecionadas as colunas que irão compor a visão da nova tabela. Sendo assim, a partir da tabela principal serão criadas as tabelas:

## Estrutura do Projeto

- **Financials_origem** (Modo oculto - backup)
- **D_Produtos**:

  - ID_produto
  - Produto
  - Média de Unidades Vendidas
  - Média do Valor de Vendas
  - Mediana do Valor de Vendas
  - Valor Máximo de Venda
  - Valor Mínimo de Venda

- **D_Produtos_Detalhes**:

  - ID_produto
  - Discount Band
  - Sale Price
  - Units Sold
  - Manufacturing Price

- **D_Descontos**:

  - ID_produto
  - Discount
  - Discount Band

- **D_Detalhes**:

  - Contém informações adicionais não contempladas nas outras tabelas de dimensão como (Gross Sales,COGS...)

- **D_Calendário**:
  - Criada com a função `CALENDAR()` do DAX
- **F_Vendas**:
  - SK_ID
  - ID_Produto
  - Produto
  - Units Sold
  - Sales Price
  - Discount Band
  - Segment
  - Country
  - Salers
  - Profit
  - Date

## Etapas de Construção

1. **Criação da Tabela Backup**:

   - Criar uma cópia da tabela original "Financial Sample" denominada "Financials_origem" e ocultá-la para backup.

2. **Criação das Tabelas de Dimensão**:

   - **D_Produtos**: Selecionar as colunas relevantes e agregar os dados para calcular métricas como médias e medianas.
   - **D_Produtos_Detalhes**: Extrair detalhes específicos dos produtos, como preço de venda e unidades vendidas.
   - **D_Descontos**: Mapear os descontos aplicados aos produtos.
   - **D_Detalhes**: Incluir quaisquer informações adicionais sobre as vendas que não foram capturadas nas outras tabelas de dimensão.
   - **D_Calendário**: Criar uma tabela de calendário utilizando a função `CALENDAR()` do DAX.

3. **Criação da Tabela de Fato**:
   - **F_Vendas**: Consolidar todas as informações de vendas, incluindo chaves estrangeiras para as tabelas de dimensão.
