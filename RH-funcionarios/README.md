# Dashboard de Análise de Dados de RH
- Com layout móvel


## Perguntas de negócio: 
 
1 - Qual o total de funcionários atualmente na empresa? 

2 - Qual o tempo médio de experiência dos funcionários (em anos)? 

3 - Qual o total e percentual de funcionários do gênero masculino e feminino? 

4 - Qual a média salarial mensal? 

5 - Qual o total de funcionários por função? 

6 - Qual o percentual de funcionários disponíveis para fazer hora extra? 

7 - Qual o nível de envolvimento dos funcionários no trabalho considerando 4 categorias: Ruim, Baixo, Médio e Alto? 


## Medidas Criadas

### Total de Funcionários
- TotalFunc = COUNTROWS(DatasetRH)

### Total de Funcionários - Feminino
- TotalFeminino = CALCULATE([TotalFunc],DatasetRH[Genero]="Feminino")

### Total de Funcionários - Masculino
- TotalMasculino = CALCULATE([TotalFunc],DatasetRH[Genero]="Masculino")

### % Masculino
- % Masculino = DIVIDE([TotalMasculino], [TotalFunc], 0) 

### % Feminino
- % Feminino = DIVIDE([TotalFeminino], [TotalFunc], 0)

### Salário Médio
- SalarioMedio = AVERAGE(DatasetRH[Salario_Mensal])

### Total de Funcionários que devem ser promovidos
- TotalFuncPromover = CALCULATE([TotalFunc],DatasetRH[StatusPromo]="Considerar Promoção Imediata")

### Total de Funcionários que não devem ser promovidos
- TotalFuncNaoPromover = CALCULATE([TotalFunc],DatasetRH[StatusPromo]="Não Considerar Promoção Imediata")

### Porcentagem de Funcionários que devem ser promovidos
- % Promover = DIVIDE([TotalFuncPromover], [TotalFunc], 0)

### Porcentagem de Funcionários que não devem ser promovidos
- % NaoPromover = DIVIDE([TotalFuncNaoPromover], [TotalFunc], 0)


## Criação de Colunas

### [StatusPromo]
~~~
if [Anos_Desde_Ultima_Promocao] >= 5 then "Considerar Promoção Imediata"
else "Não Considerar Promoção Imediata"
~~~

### [Envolvimento_Trabalho]
~~~
if [Indice_Envolvimento_Trabalho] = 1 then "Ruim"
else if [Indice_Envolvimento_Trabalho] = 2 then "Baixo"
else if [Indice_Envolvimento_Trabalho] = 3 then "Médio"
else "Alto"
~~~


## Modificação de Colunas

### [Disponivel_Hora_Extra]
- Substituir "S" por "Sim"
- Substituir "N" por "Não"

## Visualizações

- Total de Funcionários
- Salário Médio
- Funcionários do Gênero Feminino
- Percentual de Funcionários do Gênero Feminino
- Funcionários do Gênero Masculino
- Percentual de Funcionários do Gênero Masculino
- Média de Anos de Experiência
- Média de Idade
- Funcionários para Promover
- Percentual de Funcionários para Promover
- Funcionários para Não Promover
- Percentual de Funcionários para Não Promover
- Total de Funcionários por Função
- Total de Funcionários por Estado Civil
- Total de Funcionários por Disponibilidade para Hora Extra
- Total de Funcionários por Envolvimento no Trabalho
- Total de Funcionários por Viagem
