# Hexagon - Desafio

Descrição :
	Uso do(s) framework chalice, serverless e ng

Procedimentos :

 1 - Criação de um usuário para a aplicação
 
		  * IAM - Roles - Policy
		  
 2 - Criação dos Buckets no S3 

	Bucket para o Front End - Upload de arquivos : formato csv

	  2.1 - Criação do Bucket - Nome : Hexagon
	  2.2 - Configuração do Bucket como um web hosting static
	  2.3 - Geração de um boilerplate - front-end - utilizando ng , um framework angular
	  2.4 - Definição e implementação do front-end - angular
	  
	  Acesso ao front-end : 
	  Etapas 
	  
	  Back-end : 
			   Framework : Serveless
			   sls create --template aws-python --path hexagon-backend

 3 - Criação do modelo de dados no DynamoDB para persistência dos mesmos.
 
	 3.1 - Criação de um arquivo JSON com o modelo de dados a ser implementado, segue nome do arquivo:
	 
			* tabelasDynamoDb.json
	 
	 3.2 - Criação local das tabelas no DynamoDB utilizando linha de comando do sdk aws
	 
			> aws dynamodb create-table --cli-input-json file://tabelasDynamoDb.json --endpoint-url http://localhost:8000
	 
	 3.3 - Criação remota das tabelas no DynamoDB utilizando linha de comando do sdk aws
 
			> aws dynamodb create-table --cli-input-json file://tabelasDynamoDb.json --region sa-east-1

 4 - Criação da Lambda function para ler o arquivo(s) CSV 
 
		 *  Criação de um notebook com jupyter notebook para testes
 
 5 - Abertura do arquivo CSV
 
 6 - Leitura de CSV
 
 7 - Persistência dos dados lidos do(s) arquivo(s) CSV 
 
		 * Script para a persistencia dos dados lidos do CSV
 
 8 - Apresentação dos dados do CSV
 
		 * Controller-Angular.js - Leitura dos dados 
 
 9 - Aplicação de tecnicas de mineração de dados
 
		  * Uso da tecnica de agrupamento 
		  * Regras de associação
	   
10 - Geração de Graficos

		  * Uso do framework D3.js
		  * Grafico de pizza para apresentar os gastos por uma dada unidade.

11 - Preparação do Deploy

		  * Uso do CloudFormation
	   
		  aws cloudformation package 
				   --template-file C:\hexagon\markov-model\package\sam.json 
				   --s3-bucket agriculturainteligente 
				   --output-template-file C:\hexagon\markov-model\package\packaged.yaml

12 - Execução do Deploy

		  aws cloudformation deploy 
				   --template-file C:\hexagon\markov-model\package\packaged.yaml 
				   --stack-name hexagon-desafio
