## Dados IPCA

### Etapas
* Objetivo/Pergunta
* Busca e importação dos dados
* Tratamento e transformação dos dados
* Criando as tabelas
* Criação relatório
* Link código

#### Tecnologias utilizadas:

* Pyspark
* SQL
* DataBricks
* Python
* Power BI

### 1.Objetivo/Pergunta

Contexto:

Nosso cliente é o Banco IP2CA, um grande banco do mercado brasileiro de varejo com atuação há 30 anos e uma base de 50 milhões de clientes ativos.

O cliente tem impactos diretos conforme a variação do Índice de Preços ao Consumidor Amplo (IPCA) e atualmente sofre para reagir devido a seus processos lentos e manuais para captura e análise deste índice.

Diante disto, o cliente pede uma análise do IPCA desde sua fundação com geração de insights relevantes para que ele possa melhorar seu negócio.

### 2.Busca e importação dos dados

![image](https://github.com/user-attachments/assets/11f35685-269a-4515-a8cb-101e45718eb6)

* o 1º bloco, pega as bibliotecas necessárias, a requests, que é usada para fazer a requisição a API, nesse caso a API dos dados o banco central sobre IPCA.
* o 2º bloco traz os parametros necessários para conseguir extrair os dados da API
* o 3º bloco é URL da API , já com os parametros
* o 4º bloco faz a requisição, extrair os dados e já cria um spark dataframe, ainda com os dados puros

### 3.Tratamento e transformação dos dados

![image](https://github.com/user-attachments/assets/88d7449b-91d9-4cbd-8dab-74dbb503e92d)

* no 1º bloco os dados que estavam em formato de texto são convertidos para a data e decimal, a divisao por 100 acontece porque os dados não vieram no formato de % para power BI.
* no 2º bloco realizamos o calculo do IPCA acumulado (jan a dez), a criação de uma coluna de data com Ano-01-01 é usada para facilitar o relacionamento com a tabela de calendário que sará criada mais a frente
* no 3º bloco realizamos a criação do dataframe que vai calcular a média do IPCA dos últimos 5 anos, já tirando os anos da pandemia(2020,2021), feito de maneira dinamica, caso chegasse novos dados de IPCA.

### 4.Criando as tabelas

![image](https://github.com/user-attachments/assets/a0d81ddb-eb97-4bb7-a57b-00f62a85746a)

* No 1 º bloco,criamos um schema separado ,para guardar as tabelas
* No 2º bloco, criamos as tabelas fatos
* No 3º bloco cria a tabela dimensão de calendário.

### 5.Criação do relatório

![image](https://github.com/user-attachments/assets/f78614e7-d90a-48de-98bd-aa9f54347910)

![image](https://github.com/user-attachments/assets/592d3370-65cc-4d1c-b8ba-9a8f054f3149)


* Relatório contendo a média do IPCA dos últimos 5 anos (mensal e acumulado)
* IPCA acumulado por ano, desde 1994 até 2024.
* Alguns insights, observações e próximos passos.

6. Link código

![image](https://github.com/user-attachments/assets/41d59dbb-94de-441b-8d9c-a4e07c76c153)

  









