# HousePrices
Desafio de previsão de preços de casas da base House Prices do Kaggle<br>
Técnicas avançadas de regressão <br>
Submissão ficou detro do top 1500 do House Prices no Kaggle. <br>
<br><backspace><img src="https://storage.googleapis.com/kaggle-media/competitions/House%20Prices/kaggle_5407_media_housesbanner.png" width=800><br>
# Sobre a competição
- A base de dados possui 79 variáveis que descrevem aspectos das residências de Ames, Iowa.
- O Objetivo da competição é elaborar um modelo de regressão capaz de prever o preço das casas.
- A métrica considerada no desafio é o Root-Mean-Squared-Error(RMSE) considerando o logarítimo para ter a mesma penalização em erros de casas caras e baratas.
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRxDZcRHy4lOtYjOjcxhn72vPMjBGjRnPxkKA&s" width=400><br>
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
### Variável alvo (Preço das Casas)
- Em um projeto de ciência de dados é muito importante observar a distribuição da variável alvo para poder determinar os modelos que devem ser utilizados.<br>
- Podemos notar que existem valores considerados outliers, casas com valores bem mais elevados que a média.
<br><img src="https://github.com/JoseVitor-OSS/HousePrices/blob/main/imagens/Distribui%C3%A7%C3%A3o%20da%20vari%C3%A1vel%20alvo.png?raw=true" width=600><br>

### Submissão 1
- O tratamento dos dados para primeira submissão considerou apenas o preenchimento de valores vazios.
- Esse procedimento foi realizado analisando a descrição da base, é necessário entender se os valores nulos são problemas da mesma.
- Foram consideradas apenas as features numéricas nesta etapa.
- Seleção de características:
  - Para os dois primeiros modelos foi considerado a importancia das features fornecida pelos próprios.
  - Para o modelo Lasso, as importâncias das features deve ser obtida apenas após sua normalização.
- Após ordenar as features por importâncias, foram treinados os modelos aumentando a quantidade de features gradativamente (seguindo a ordem de importância).
- Dessa forma foi possível observar o fenômeno da maldissão da dimensionalidade, onde o modelo começa a reduzir o score a medida que são implementadas mais features.
<br>&nbsp;&nbsp;&nbsp;<img src="https://github.com/JoseVitor-OSS/HousePrices/blob/main/imagens/Maldi%C3%A7%C3%A3o%20da%20dimensionalidade.png?raw=true" width=500><br>
- Então o modelo considerando todas as features não teria o desempenho máximo e ainda custaria mais computacionalmente.
- De cada modelo foram filtradas a quantidade de features onde apresenta melhor desempenho e em seguida comparados.
<br>&nbsp;&nbsp;&nbsp;<img src="https://github.com/JoseVitor-OSS/HousePrices/blob/main/imagens/Compara%C3%A7%C3%A3o%20de%20desempenho%20sub%201.png?raw=true" width=300><br>
- Ainda podemos comparar os valores preditos dos valores reais para cada modelo.
  - É interessante notar que os modelos tem um problema em predizer valores elevados para as casas, existe um limite aproximadamente em 500.000.
  - Isso pode ser explicado pela forma como os modelos estão penalizando valores distantes da média.
  - Por padrão os modelos estão penalizando considerando o erro quadrado, isso faz com que valores distantes tenham peso muito menor.
  - Isso pode ser modificado considerando a necessidade do negócio.
  - Aqui não foi modificado.
<br>&nbsp;&nbsp;&nbsp;<img src="https://github.com/JoseVitor-OSS/HousePrices/blob/main/imagens/Maldi%C3%A7%C3%A3o%20da%20dimensionalidade.png?raw=true" width=500><br>
### Representação gráfica da previsão dos 3 melhores modelos
<img  src="https://raw.githubusercontent.com/JoseVitor-OSS/HousePrices/main/Resultado/Melhores_modelos.png" />

### Score da submissão
<img  src="https://github.com/JoseVitor-OSS/HousePrices/blob/main/Resultado/image.png?raw=true"/>

