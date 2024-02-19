# Laboratorio AI 900

## Descrição

Entrei no [site do microsoft azure](ml.azure.com), e usei um treinamento de máquina automático para treinar um modelo, com base nos passos desse [site da microsoft](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)

## Passos importantes

- 1: Criei um ML automatizado chamado "mslearn-bike-automl2", com nome do experimento de "mslearn-bike-rental"
- 2: Selecionei o tipo de tarefa como "regressão", com tipo de dado com o nome de "bike-rentals" e tipo "tabular", a fonte dos dados foi via arquivos web, com o link "mslearn-bike-rental"
- 3: As configurações da tarefa tiveram como métrica primária o "Normalized root mean squared error" e com os modelos "RandomForest" e "LightGBM" permitidos
- 4: Os limites para a tarefa eram de 3 tentativas máximas, 3 tentativas simultâneas, 3 nós máximos, limite da pontuação métrica de 0.085, tempo limite de 15 minutos e tempo limite de interação de 15 minutos também
- 5: Vi qual foi o modelo que se saiu melhor e implantei um serviço web, com base nele, com o nome de "predict-rentals" e tipo de computação "Azure Container Instance"
- 6: Testei o implantamento com o código abaixo
```
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
 ```

 ## Passos para chegar ao resultado 443.22799243245083

 - 1: Fui no ML automatizado que criei e cliquei no algorítimo com melhor modelo
 - 2: Fui testando o modelo com diferentes tipos de características baseados nos dias, meses e climas