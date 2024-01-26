# Dashboard de Covid-19 no Brasil 
- (25 de Fevereiro de 2020 - 28 de Outubro de 2023)


## Bases de dados
- Fonte: https://covid.saude.gov.br/


## Importar bases de dados
- Problemas com acentuação gráfica
	- Modificar Origem do Arquivo para "65001: Unicode (UTF-8)"


## Juntar bases de dados
- Importar todas as bases de dados
- Power Query: Acrescentar Consultas>Acrescentar Consultas como Novas
- Selecionar "Três ou mais tabelas" > Selecionar e adicionar todas
- Renomear para "covidbr_2020_20231"


## Coluna [estado]
- Substituir valores faltantes por "NÃO INFORMADO"
- Base de dados: covidbr_2020_20231


## Coluna [municipio]
- Substituir valores faltantes por "Não Informado"
- Base de dados: covidbr_2020_20231


## Medidas criadas

- n_casos = 
CALCULATE(SUM('covidbr_2020_2023-28out'[casosAcumulado]), FILTER('covidbr_2020_2023-28out','covidbr_2020_2023-28out'[data]=max('covidbr_2020_2023-28out'[data])) ) 

- n_casos_novos = 
CALCULATE(SUM('covidbr_2020_2023-28out'[casosNovos]), FILTER('covidbr_2020_2023-28out','covidbr_2020_2023-28out'[data]=max('covidbr_2020_2023-28out'[data])) ) 

- n_obitos = 
CALCULATE(SUM('covidbr_2020_2023-28out'[obitosAcumulado]), FILTER('covidbr_2020_2023-28out','covidbr_2020_2023-28out'[data]=max('covidbr_2020_2023-28out'[data])) ) 

- n_obitos_novos = 
CALCULATE(SUM('covidbr_2020_2023-28out'[obitosNovos]), FILTER('covidbr_2020_2023-28out','covidbr_2020_2023-28out'[data]=max('covidbr_2020_2023-28out'[data])) ) 
