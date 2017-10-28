# Hexagon

Repositorio utilizado para o Hexagon-Desafio 

Uso do(s) framework chalice, serverless e ng

Procedimentos :

         1 - Criação de um usuario com as permissões
         
                  * IAM - User - Policy
                  
         2 - Criação do S3 - bucket para o upload de arquivo(s) CSV - Front End em Angular.js
         
                  https://s3.console.aws.amazon.com/s3/buckets/agriculturainteligente/?region=us-east-1
         
                  * Geração do arquivos do Front-End Angular.js
         
         3 - Criação do DynamoDB para persistir os dados dos arquivos CSV
                  
                  * Script para a geração da(s) tabelas, collection e itens
         
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
