## Dados IPCA

### Etapas
* Objetivo/Pergunta
* Busca e importação dos dados
* Tratamento e transformação dos dados
* Criação relatório
* Link código
* Arquivo pbix(Power BI Desktop)

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


