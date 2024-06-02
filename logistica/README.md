# Dashboard de Análise de Dados de Logística
- Com layout móvel


## Medidas criadas

### Total de Entregas
- TotalEntregas = COUNTROWS(Logistica)

### Rating
- Classificação de rating 
- Criada em novas medidas rápidas
    - Novas medidas rápidas
    - Classificação por estrelas
    - Valor base: TotalEntregas
    - Número de estrelas: 5
    - Valor menor: 1500
    - Valor maior: 2500

```
Rating2 = 
VAR __MAX_NUMBER_OF_STARS = 5
VAR __MIN_RATED_VALUE = 1500
VAR __MAX_RATED_VALUE = 2300
VAR __BASE_VALUE = [TotalEntregas]
VAR __NORMALIZED_BASE_VALUE =
	MIN(
		MAX(
			DIVIDE(
				__BASE_VALUE - __MIN_RATED_VALUE,
				__MAX_RATED_VALUE - __MIN_RATED_VALUE
			),
			0
		),
		1
	)
VAR __STAR_RATING = ROUND(__NORMALIZED_BASE_VALUE * __MAX_NUMBER_OF_STARS, 0)
RETURN
	IF(
		NOT ISBLANK(__BASE_VALUE),
		REPT(UNICHAR(9733), __STAR_RATING)
			& REPT(UNICHAR(9734), __MAX_NUMBER_OF_STARS - __STAR_RATING)
	)
```


### Total de Entregas no Prazo
- TotalEntregasPrazo = CALCULATE([TotalEntregas], FILTER(Logistica, Logistica[Status_Entrega] = "Antecipado" || Logistica[Status_Entrega] = "No Prazo"))


## Visualizações

### Total de Entregas no Prazo por Canal de Entrega
- Gráfico de área
- Usar filtro
    - [Status_Entrega] = No Prazo

### Percentual de Entregas por Equipe
- Gráfico de barras

### Total de Entregas por Mês
- Gráfico de linha

### Total de Entregas por Top 5 Vendedores
- Tabela
- Usar filtro
    - N superior>Superior 5>[TotalEntregas]
- Classificação de rating 

### Total de Entregas com Atraso por Cidade
- Tabela
- Usar filtro
    - [Status_Entrega] = Atrasado

### Percentual de Entregas por Status de Entrega
- Gráfico de barras

### Total de Entregas
- Cartão

### Total de Entregas no Prazo
- Cartão

### Ano - Filtro
- Visual Chiclet Slicer (Microsoft Corporation)
- Botões
