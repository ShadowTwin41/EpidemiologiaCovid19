# Epidemiologia 
 # Dados do Covid-19 Brasil e Mundo
 

 
Os dados são descarregados de diferentes locais para tentar disponibilizar a informação da forma mais completa e diversificada.
Os processos de criação dos Mapas e Gráficos é completamente automática se primeiro se fizer os devidos descarregamentos. [getDataBrazil.ipynb](EpidemiologiaCovid19/Andre/Covid-19Brazil/getDataBrazil.ipynb)
Este ficherio também guarda todos os dados numa base de dados PostGre.

Qualquer melhoramento ou deteção de erros é sempre bem vinda!

## Origem dos dados

https://github.com/wcota/covid19br - Informação relativa ao número de infetados, recuperados, entre outros dados sobre o Brasil.
https://github.com/CSSEGISandData/COVID-19 - Informação relativa aos dados em todo o Mundo.

Os dados para construção dos Mapas em Qgis (PyQgis) foram obtidos:
https://www.ibge.gov.br/geociencias/downloads-geociencias.html - Brasil
https://www.naturalearthdata.com/downloads/10m-cultural-vectors/10m-admin-0-countries/ - Mundo

## Atalhos
[Estudo do Brasil](Andre/Covid-19Brazil/)
- [Imagens](Andre/Covid-19Brazil/fig)
- [Dados](Andre/Covid-19Brazil/Tables)
- [Modelos Matemáticos](Andre/Covid-19Brazil/ML)

[Teste do PyQgis](Andre/qgis.ipynb)

[Teste de SQL](Andre/SQL)

[Exercícios Propostos](Andre/Exercicos)

## Brasil - Casos confirmado por Estado

Estes mapas podem ser criado a partir do software Qgis ou recorrendo ao codigo publicado [mapsBrasil.ipynb](EpidemiologiaCovid19/Andre/Covid-19Brazil/mapsBrasil.ipynb) que utiliza biblitecas PyQgis. Para se conseguir utilizar tem-se que instalar todos os esses packages e configurar corretamente, existem vários tutoriais pela internet. Para testar se tudo está bem configurado sugere-se correr o ficheiro [qgis.ipynb](EpidemiologiaCovid19/Andre/qgis.ipynb).

![Casos por Estado](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/brasilCases.png)

[Dataset Utilizado](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/Tables/cases-brazil-total.csv)

## Brasil - Casos por Municípios
É importante notar que nem toda a informação se encontra disponível, provavlemente pelo facto de a secretaria estadual ainda não ter  confirmado esses casos ou não existe casos e, como tal, não foram considerados esses locais no Dataset
![Casos por Municipio](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/brasilCasesn.png)

[Dataset Utilizado](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/Tables/cases-cities.csv)
Este dataset teve que ser processado para que tivesse a funcionalidade pretendida.

### Mapa com graduação de cor
Neste caso, quanto mais vermelho for a cor mais casos tem. A verde está representado os municípios com mais casos conformados (a cor serve para se destacarem mais facilmente). A azul estão os municípios sem dados associados.

Para se realizar este mapa foi necessário dois layers distintos, em que um correspondia ao layer com o mapa térmico, mas sem aparecer os municípios sem dados, e o segundo (colocado sob o primeiro layer) em que correspondia ao mapa normal a azul.
![Casos por Municipio](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/brasiloverlayer.png)

[Dataset Utilizado](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/Tables/cases-cities.csv)

[GeoPackage](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/Tables/brasil.gpkg)

## Mundo - Casos Confirmados
Neste mapa foram utlizados dois layers distintos, um com o mapa do mundo sob um outro com os casos confirmados de Covid-19 a nível mundial. Para este processamento utilizou-se o software Qgis com o qual se definiu todos os labels e guardado num package [world.gpkg](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/Tables/world.gpkg)

![Casos Mundo](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/worldCases.png)


[Dataset Utilizado](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/Tables/cases_country.csv)

[GeoPackage](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/Tables/world.gpkg)



## Animação com casos confirmados 
Com o software Qgis foi possivel criar um video que presenta o aumento de casos confirmados ao longo do tempo.

[Watch the video](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/bandicam%202020-05-12%2017-02-45-285.mp4)


# Dados estatísticos

Com os datasets recolhidos também foram criados alguns gráficos de forma a ser mais visivel os números de casos confirmados. Utilizaram-se as bibliotecas "pandas" "matplotlib" e "numpy" para se conseguir visualizar os dados.

De seguida é apresentado um gráfico de barras em que está ordenado o número de casos em cada estado. A barra do total não apresenta o valor máximo.

## Brasil - Número de casos confirmados
![Casos Mundo](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/numberCases.jpg)

### Brasil - Número de casos confirmados - pie
![Casos Mundo](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/pieBrasil.jpg)

## Mundo - Maiores valores de infetados a nível mundial
Gráfico com os países com mais casos confirmados, para se comparar com o Brasil.
![Casos Mundo](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/worldnumberCases.jpg)

### Mundo - Número de casos confirmados - pie
![Casos Mundo](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/pie.jpg)

### Mundo - Número de casos confirmados
De seguida é apresentado um gráfico de barras em que é apresentado o número de casos confirmados por dia. Verifica-se um aumento exponêncial.
![Casos Mundo](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/world_number_cases.jpg)


