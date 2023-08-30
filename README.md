# projeto-imoveis
Em uma simulação, fui contratado como cientista de dados para dar suporte à equipe de Machine Learn e Dev. Minha função era importar, tratar e preparar a base de dados para posterior análise. Lançou-se mão do Jupyter Notebook, importando a biblioteca do Pandas, para executar todas as informações solicitadas.

## Habilidades Desenvolvidas
A partir da base dados, com valores fictícios, extraída do  <a href="[https://grouplens.org/datasets/movielens/](https://raw.githubusercontent.com/alura-cursos/pandas-conhecendo-a-biblioteca/main/base-de-dados/aluguel.csv)https://raw.githubusercontent.com/alura-cursos/pandas-conhecendo-a-biblioteca/main/base-de-dados/aluguel.csv" target="_blank"> Aluguel de Imóveis</a> obtemos o DataFrame:

![image](https://github.com/KelsonHenrique/projeto-imoveis/assets/141082201/68d497a8-8bf0-4a3f-98c9-0aa7a22658c8)

A primeira informação solicitada pela equipe de Machine Learning foi o Valor Médio por tipo de imóvel. Nesse sentido, usou-se o método "Groupby" e do "Mean", seguidos de "numeric_only=True", para especificar que esse método é válido apenas para colunas numéricas. 
```
dados.groupby('Tipo').mean(numeric_only=True)
```
Obtemos o seguinte DataFrame:
![image](https://github.com/KelsonHenrique/projeto-imoveis/assets/141082201/62b818d3-b5eb-4cc4-b323-4ffe1047cd7f)

