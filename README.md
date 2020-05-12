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

## Brasil - Casos confirmado por Estado


Estes mapas podem ser criado a partir do software Qgis ou recorrendo ao codigo publicado [mapsBrasil.ipynb](EpidemiologiaCovid19/Andre/Covid-19Brazil/mapsBrasil.ipynb) que utiliza biblitecas PyQgis. Para se conseguir utilizar tem-se que instalar todos os esses packages e configurar corretamente, existem vários tutoriais pela internet. Para testar se tudo está bem configurado sugere-se correr o ficheiro [qgis.ipynb](EpidemiologiaCovid19/Andre/qgis.ipynb).

![Casos por Estado](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/brasilCases.png)

## Brasil - Casos por Municípios
É importante notar que nem toda a informação se encontra disponível, provavlemente pelo facto de a secretaria estadual ainda não ter  confirmado esses casos ou não existe casos e, como tal, não foram considerados esses locais no Dataset
![Casos por Municipio](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/brasilCasesn.png)

[Dataset Utilizado]() 

### Mapa com graduação de cor
Neste caso, quanto mais vermelho for a cor mais casos tem. A verde está representado os municípios com mais casos conformados (a cor serve para se destacarem mais facilmente). A azul estão os municípios sem dados associados.

Para se realizar este mapa foi necessário dois layers distintos, em que um correspondia ao layer com o mapa térmico, mas sem aparecer os municípios sem dados, e o segundo (colocado sob o primeiro layer) em que correspondia ao mapa normal a azul.
![Casos por Municipio](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Covid-19Brazil/fig/brasiloverlayer.png)

## Mundo - Casos Confirmados
Neste mapa foram utlizados
	1.O Primeiro apenas verifica que se consegue utilizar as ferramentas do QGIS no python; 
[qgis.ipynb](Andre/qgis.ipynb)
	
	2.O Segundo utiliza comando sql para obter informação do PostGreSQL. 
[connect_database_postgres.ipynb](Andre/SQL/connect_database_postgres.ipynb)

