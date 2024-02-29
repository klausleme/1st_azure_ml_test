# Treinando um modelo de machine learning automatizado

## Desafio DIO usando Azure

### 1 - Acessando o Azure Machine Learning studio, na página Automated ML, criei um Job Automatizado ML com as seguintes configurações:

**Basic settings:**

  Job name: mslearn-bike-automl
  New experiment name: mslearn-bike-rental
  Description: Automated machine learning for bike rental prediction
  Tags: none

**Task type & data:**

  Select task type: Regression
  Select dataset: Create a new dataset with the following settings:
  
  **Data type:**
      Name: bike-rentals
      Description: Historic bike rental data
      Type: Tabular
      
  **Data source:**
  Select From web files
      
  **Web URL:**
  Web URL: https://aka.ms/bike-rentals
  Skip data validation: do not select
      
  **Settings:**
  
  File format: Delimited
  Delimiter: Comma
  Encoding: UTF-8
  Column headers: Only first file has headers
  kip rows: None
  Dataset contains multi-line data: do not select
  
  **Schema:**
  Include all columns other than Path
  Review the automatically detected types

Depois que o conjunto de dados for criado, selecionei o conjunto de dados bike-rentals para continuar a submeter o trabalho de ML automatizado.

 Ao submeter o job, ele começará automaticamente.

### 2 - Implementando o melhor modelo

Na guia Model para obter o melhor modelo treinado pelo seu trabalho de aprendizado de máquina automatizado, selecione DEploy e usar a opção Web Service para implantar o modelo com as seguintes configurações:

Name: predict-rentals
Description: Predict cycle rentals
Compute type: Azure Container Instance
Enable authentication: Selected

### 3 - Testando o serviço implementado

Ao selecionar Endpoints e abrir o predict-rentals endpoint em tempo real, aparece a aba Test.

Ao implementar o código da documentação:

         {
     "Inputs": { 
       "data": [
         {
           "day": 1,
           "mnth": 1,   
           "year": 2022,
           "season": 2,
           "holiday": 0,
           "weekday": 1,
           "workingday": 1,
           "weathersit": 2, 
           "temp": 0.3, 
           "atemp": 0.3,
           "hum": 0.3,
           "windspeed": 0.3 
         }
       ]    
     },   
     "GlobalParameters": 1.0
   }

Obteve-se o resultado:

    {
      "Results": [
        364.78935594629985
      ]
    }











  
