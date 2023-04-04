# Data Engineer Project
Colocando alguns estudos em prática com um pequeno projeto de Engenharia de Dados.

# Diagrama Abstrato do Projeto
![Diagrama02](https://user-images.githubusercontent.com/115668126/229661801-96b7cf74-cb63-47c4-aecb-46019c635a67.png)

### *Análise Geral - Projeto de Engenharia de Dados para estudo*
- Efetuar o download de arquivos da web com Python.
- Inserir dados de um dataframe na cloud Azure com Azure SQL Database.
- Efetuar transformações nos dados com Azure Data Factory.



***1º Etapa***

Pegue algum site da Web que tenha um arquivo em algum formato (.csv, .txt,...) e faça o download dele com Python.

Utilizei a biblioteca requests, é uma das bibliotecas mais populares em Python para fazer requisições HTTP. Ela permite que você envie requisições HTTP com facilidade e é muito simples de usar.

1.	Biblioteca importada
2.	Criação de uma função para baixar o arquivo.
3.	Variável que faz requisição ao servidor HTTP
4.	Estrutura With Open para abrir o arquivo e ser fechado automaticamente após a conclusão.
5.	Atributo .content para escrever os dados no arquivo.

![Requests](https://user-images.githubusercontent.com/115668126/229662162-61974415-7fa3-4b86-9d85-eac49e9e7a62.png)

6.	Arquivo baixado.
![Csvfile](https://user-images.githubusercontent.com/115668126/229662258-cd7bb794-1099-4543-ad32-efbbd222a910.png)


***2º Etapa***

Faça a ingestão dos dados em uma base de dados da cloud Azure usando o Azure SQL Database.

1.	Resource group criado no ambiente cloud Microsoft Azure.

![RG](https://user-images.githubusercontent.com/115668126/229662468-cfdb23d7-a9f7-4d6d-a221-9723b04e5e4d.png)

2.	Criação do Banco de Dados e Servidor SQL Azure.

![SVandDB](https://user-images.githubusercontent.com/115668126/229662684-a6e357ff-e071-401a-a3c6-0632e6ce3cb4.png)

3.	Conexão com o Banco de Dados no Azure Data Studio.

![AzureDataStudio](https://user-images.githubusercontent.com/115668126/229662786-3517059f-7095-4faa-adba-a185b9d0b581.png)

4.	Extensão SQL Server Import Instalada para importação do arquivo .csv

![SQLImport](https://user-images.githubusercontent.com/115668126/229662889-a607bcd7-195b-4979-afa2-b035120e953f.png)

5.	Importando arquivo na Base de Dados.

![ImportCSVWizard](https://user-images.githubusercontent.com/115668126/229662965-65d10acb-f284-4cd8-a198-45968016dee3.png)

6.	Ingestão de dados concluída.

![Import01](https://user-images.githubusercontent.com/115668126/229663056-77bc7d48-cb92-4f95-9513-44329c033351.png)
![Import02](https://user-images.githubusercontent.com/115668126/229663067-a0d40580-e0c7-4ac6-85bf-0ca2b165d4f2.png)


***3º Etapa***

Faça algumas transformações nesses dados (trocar type das colunas, agrupamentos,...) usando o Azure Data Factory.

1.	Data Factory criado.

![adf](https://user-images.githubusercontent.com/115668126/229663202-656a8cca-3c75-4e50-89a6-8b72733cc179.png)

2.	Utilizei o Query Editor para análise da tabela.

![QueryEditor](https://user-images.githubusercontent.com/115668126/229663410-b1c3c2dd-e64c-4941-9fba-ede0da1b3e3d.png)

3.	Linked Service criado. (Realiza a conexão para uma determinada fonte de dados que desejamos utilizar.)

![LinkedService](https://user-images.githubusercontent.com/115668126/229663467-2f6b92c9-8bb9-4191-ab3e-7e8e57567905.png)

4.	Dataset genérico criado com dois parâmetros – (schemaName) | (tableName)

![Dataset01](https://user-images.githubusercontent.com/115668126/229663598-967c2f51-2565-4bf8-8096-b81ee534a557.png)
![Dataset02](https://user-images.githubusercontent.com/115668126/229663613-d6b69b2f-e91a-43bc-8009-5e338d3663d6.png)

5.	Criei um DataFlow que permite desenvolver uma lógica de transformação de dados que pode ser executada como Activies dentro dos Pipelines.

![Dataflow](https://user-images.githubusercontent.com/115668126/229663726-f86efb2e-2bc3-4526-bc38-f414716f32be.png)

6.	Pipeline executado junto ao DataFlow.

![PipelineDF](https://user-images.githubusercontent.com/115668126/229663810-603ea7a6-64b9-4170-8706-1be266f2b289.png)
![PipelineDFFinaly](https://user-images.githubusercontent.com/115668126/229663853-4d07ed0e-4c10-4546-a5e0-6ae384fbeb36.png)



