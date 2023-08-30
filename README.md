# Projeto-imoveis
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

Como queremos apenas saber as médias dos aluguéis, vamos selecionar apenas a coluna "Valor"
```
dados.groupby('Tipo').Valor.mean()
```
![image](https://github.com/KelsonHenrique/projeto-imoveis/assets/141082201/337d7f03-3106-490b-8dcc-6c15fe78c83d)

Para tornar a apresentação desses dados mais atraentes, usamos o seguinte comando:
```
dados.groupby('Tipo')[['Valor']].mean().sort_values('Valor')
```
Para obter:
![image](https://github.com/KelsonHenrique/projeto-imoveis/assets/141082201/b01c422d-ef5a-4dbd-bdc1-3529ce193bd0)



A equipe de Machine Learning percebeu que seria mais interessante trabalhar apenas com imóveis residenciais. Então, iniciando o tratando do banco para selecionar os imóveis:

```
imoveis_comerciais = ['Conjunto Comercial/Sala','Prédio Inteiro','Loja/Salão',
       'Galpão/Depósito/Armazém', 'Casa Comercial','Terreno Padrão', 'Box/Garagem',
       'Loja Shopping/ Ct Comercial', 'Chácara', 'Loteamento/Condomínio',
       'Sítio', 'Pousada/Chalé','Hotel', 'Indústria']
```

```
dados.query('@imoveis_comerciais not in Tipo')
```
![image](https://github.com/KelsonHenrique/projeto-imoveis/assets/141082201/a8194fcc-a475-4009-a4bc-ceef28d61fcc)

A segunda solicitação foi encontrar o Percentual de cada tipo de imóvel na nossa base de dados?
Usamos o comando:
```
df.Tipo.value_counts(normalize=True).to_frame().sort_values('Tipo')
```
E obtemos:
![image](https://github.com/KelsonHenrique/projeto-imoveis/assets/141082201/70495635-1ebe-4bac-a809-52e8b140ee20)

A equipe de Dev pediu que fosse feito o tratamento dos dados nulos:
O primeiro passo é verificar a existência de dados nulos

````
df_ap.isnull().sum()
```
![image](https://github.com/KelsonHenrique/projeto-imoveis/assets/141082201/fdb5d069-f649-4ff8-a4d6-3ba2be433623)

O segundo passo é transformá-los em "0", para esse projeto, especificamente.

```
df_ap.fillna(0)
```
![image](https://github.com/KelsonHenrique/projeto-imoveis/assets/141082201/9d00a811-a530-4ac8-9055-29ec1de86c93)


