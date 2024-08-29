# HousePrices
Desafio de previsão de preços de casas da base House Prices do Kaggle<br>
Técnicas avançadas de regressão <br>
Submissão ficou detro do top 1500 do House Prices no Kaggle. 
<br><img src="https://storage.googleapis.com/kaggle-media/competitions/House%20Prices/kaggle_5407_media_housesbanner.png" width=800><br>
# Sobre a competição
- A base de dados possui 79 variáveis que descrevem aspectos das residências de Ames, Iowa.
- O Objetivo da competição é elaborar um modelo de regressão capaz de prever o preço das casas.
- A métrica considerada no desafio é o Root-Mean-Squared-Error(RMSE) considerando o logarítimo para ter a mesma penalização em erros de casas caras e baratas.
<br><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRxDZcRHy4lOtYjOjcxhn72vPMjBGjRnPxkKA&s" width=600><br>
## Metodologia adotada
- Foram realizadas 5 submissões durante o projeto.
- As submissões podem ser divididas em 3 etapas distintas onde o tratamento dos dados foram evoluindo.
- Após análise da base de dados e seguindo a dica do próprio desafio, foram adotados 3 algoritmos de regressão.
  - Gradiente Boosting (Indicado pelo próprio desafio)
  - XGBooster
  - Lasso
## Recursos utilizados
- Tratamento de valores nulos.
- Feature engineering.
    - OrdinalEncoder.
    - One Hot Encoder.
    - Binarização.
    - Transformação de features.
    - Redução de cardinalidade.
 - Seleção de características.
 - Otmização de hiperparâmetros.
 - Cross Validation.
### Submissão 1
- O tratamento dos dados para primeira submissão considerou apenas o preenchimento de valores vazios e as features numéricas.
### Representação gráfica da previsão dos 3 melhores modelos
<img  src="https://raw.githubusercontent.com/JoseVitor-OSS/HousePrices/main/Resultado/Melhores_modelos.png" />

### Score da submissão
<img  src="https://github.com/JoseVitor-OSS/HousePrices/blob/main/Resultado/image.png?raw=true"/>

