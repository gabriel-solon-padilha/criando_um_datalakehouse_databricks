# Criando um datalakehouse usand o databricks

## Introdução

Meu décimo primeiro projeto em que usei o databricks para criar um datalakehouse usando computação distribuída e o banco de dados northwind. Nesse projeto consegui me aprofundar no uso de bibliotecas como pyspark e Koalas para computação distribuída quem usam hadoop e hive.

## Desenvolvimento

Objetivo do projeto era criar um datalakehouse com 3 camadas, sendo elas:
- 1 camada raw: contento as 11 tabelas do northwind em csv sem nenhum tipo de tratamento
- 2 camada trusted: contendo as 11 tabelas do northwind em parquet para uso dos times de ciência de dados
- 3 camada refined: contendo um datawarehouse com arquivos no formato delta e usando um starchema para tanto o time de ciência de dados como de analistas de negócio consumirem

## Resultado

Datalakehouse foi criado todo com notebooks do databricks e usando pyspark e koalas. Na camada trusted e na camada refined foram criadas tabelas externas apontando para os respectivos diretórios das camadas. Na cada refined o datawerehouse foi construído a partir da seguinte estrutura de tabelas do northwind e ficou com o seguinte schema. Foi adicionado um quarto notebook databricks de análises para testar o uso das camadas. 

**Database schema**

![Data base](https://github.com/gabriel-solon-padilha/criando_um_datalakehouse_databricks/blob/main/images/northwind_database_schema.png)

**Datawerehouse star schema**

![Data werehouse](https://github.com/gabriel-solon-padilha/criando_um_datalakehouse_databricks/blob/main/images/Datawarehouse%20star%20schema.drawio.png)

### Arquivos

- data_lakehouse_project :arrow_right: notebooks databricks que foram usados para criar o datalakehouse
- csv_tables :arrow_right: tabelas do database northwind que serão usadas no projeto e devem ser carregadas no databricks
- images :arrow_right: imagens de squema do database e do datawerehouse
- html_notebooks :arrow_right: notebooks databricks que foram usados para criar o datalakehouse porém em formato HTML para abrir pelo próprio navegador
