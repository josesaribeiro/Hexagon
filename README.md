# Hexagon

Repositorio utilizado para o Hexagon-Desafio 

Uso do(s) framework chalice, serverless e ng

Procedimentos :

         1 - Criação de um usuario com as permissões
         
                  * IAM - User - Policy
                  
         2 - Criação do S3 - bucket para Front End - Upload de arquivos : formato csv

                  2.1 - Criação do Bucket - Nome : agriculturainteligente
                  2.2 - Configuração do Bucket como um web hosting static
                  2.3 - Geração de um boilerplate - front-end - utilizando ng , um framework angular
                  2.4 - Definição e implementação do front-end - angular
                  
                  Acesso ao front-end : 
         

         3 - Criação do DynamoDB para persistir os dados dos arquivos CSV
                  
                  * Script para a geração da(s) tabelas, collection e itens
                  
                  aws dynamodb create-table 
                           --table-name Diarias 		
                           --attribute-definitions 
                                    AttributeName=CodigoOrgaoSuperior,AttributeType=S	
                                    AttributeName=NomeOrgaoSuperior,AttributeType=S	
                                    AttributeName=COdigoOrgaoSubordinado,AttributeType=S	
                                    AttributeName=NomeOrgaoSubordinado,AttributeType=S	
                                    AttributeName=COdigoUnidadeGestora,AttributeType=S	
                                    AttributeName=NomeUnidadeGestora,AttributeType=S	
                                    AttributeName=COdigoFuncao,AttributeType=S	
                                    AttributeName=NomeFuncao,AttributeType=S	
                                    AttributeName=COdigoSubfuncao,AttributeType=S	
                                    AttributeName=NomeSubuncao,AttributeType=S	
                                    AttributeName=COdigoPrograma,AttributeType=S	
                                    AttributeName=NomePrograma,AttributeType=S	
                                    AttributeName=COdigoAcao,AttributeType=S	
                                    AttributeName=NomeAcao,AttributeType=S	
                                    AttributeName=LinguagemCidada,AttributeType=S	
                                    AttributeName=CPFFavorecido,AttributeType=S	
                                    AttributeName=NomeFavorecido,AttributeType=S	
                                    AttributeName=Documento,AttributeType=S 
                                    AttributeName=Pagamento,AttributeType=S	
                                    AttributeName=GestaoPagamento,AttributeType=S	
                                    AttributeName=DataPagamento,AttributeType=S	
                                    AttributeName=ValorPagamento,AttributeType=S
                           --key-schema 
                                    AttributeName=CPFFavorecido,KeyType=HASH 
                                    AttributeName=NomeFavorecido,KeyType=RANGE 
                           --provisioned-throughput ReadCapacityUnits=10, WriteCapacityUnits=5
         
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
