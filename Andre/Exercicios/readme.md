# Exercício QGIS
[Exercicios aula](https://github.com/jgrocha/covid-pt/blob/master/Jupyter/Ponto%20da%20Situa%C3%A7%C3%A3o%20em%20Percentagem.ipynb)
Considere o "Ponto da Situação", como apresentado pela DGS. Na imagem, o ponto da situação refere-se a 14 de maio de 2020. Estes dados aparecem agregados pelas regiões do Continente, designadas NUTS II, segundo a Nomenclatura das Unidades Territoriais para Fins Estatísticos (NUTS), estabelecida para a União Europeia.

![Numero de Casos Fornecdio pela DGS](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Exercicios/DGS.PNG)

O Norte aparece com muitos mais casos do que as outras regiões. Será que assim é?

## Resolução

Para a resolução deste exercício foi necessário a construção de um ficheiro .csv com a informação relativa a cada região (Norte, Centro, Lisboa, Alentejo e Algarve).

[Dataset com o número de casos *10^6 a dividir pela quantidade de população](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Exercicios/sad.csv).

Os dados deste dataset foram retirados do site da DGS no dia 18/05/2020 para o número de casos confirmados por região e, a população, foi retiros de [Censos 2011](http://mapas.ine.pt/download/index2011.phtml).

De seguida procedeu-se ao carregamento do .csv e do mapa de portugal continental para o QGIS. O mapa foi obtido de [GeoPackage](https://render.githubusercontent.com/covid-pt-latest.gpkg). Como este mapa apresentava divisão por distritos foi necessário junta-los seguindo os limites de cada região. Para isso foi utilizado a ferramenta de seleção do QGIS e selecinou-se, inicialmente, todos os distritos do Norte e criado um novo layer com a feramenta "Agregar" da "Geometria vetorial", selecionando a opção de "Apenas os elementos selecionados". Procedeu-se a este método para as restantes regiões.

No final, colocou-se pontos no mapa e definiu-se o tamanho dependendo do valor correspondente no dataset .csv.
![Casos por milhão de pessoas](https://github.com/ShadowTwin41/EpidemiologiaCovid19/blob/master/Andre/Exercicios/fig.PNG)
