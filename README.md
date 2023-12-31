# dataimescr

O package DataImescR  permite acessar e manipular os dados do repositório de dados do IMESC de maneira simples e ágil por meio do R ou do RStudio.

A sintaxe para fazer a requisição dos dados é a seguinte.

	library(devtools)
	install_github("dataimesc/dataimescr/dataimesc")
	require(dataimesc)
	#a função get_data recebe 3 parâmetros get_data(serie=numero_da_serie,begin=ano_inicial,end=ano_final, geo="City",geo.filter="2100204")
	table<-get_data(serie=100,	
 			begin=2015,	
    		end=2019,	
       		geo="Brazil",
	 		geo.filter="BR")	
	print(table)
* O parâmetro geo é opcional e pode assumir os valores de "Brazil", "States", "Region", "City". Caso não seja especificado, o default é o parâmetro City.
* O parâmetro geo.filter é opcional e recebe o código do recorte territorial desejado Ex.("BR","ES","NE","2100204")

O resultado será semelhante ao seguinte.

![image](https://github.com/dataimesc/dataimesc_library/assets/137085586/5389a821-bb94-4a50-83aa-98fa30abe330)

Caso deseje consultar informações sobre uma série, você pode utilizar a função info_imesc cuja chamada é dada pela seguinte forma
```
library(devtools)
install_github("dataimesc/dataimescr/dataimesc")
require(dataimesc)
#No parâmetro serie você inputa o número da série que você deseja receber informações
data<-dataimesc::info_imesc(serie=100)
print(data)
```
![image](https://github.com/dataimesc/dataimescr/assets/137085586/be383acc-869f-446e-8399-4d15a9038fef)
