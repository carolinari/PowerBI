<h1>Dashboard de Produção</h1>

Conjunto de dados: Produção.xlsx

<h3>Dashboard com:</h3>
<ul>
  <li>Total produzido</li>
  <li>Total rejeitado</li>
  <li>Horas produtivas</li>
  <li>Horas paradas</li>
  <li>Total produzido por mês</li>
  <li>Produtividade</li>
  <li>Qualidade</li>
  <li>Operador (desempenho)</li>
  <li>Mês (desempenho)</li>
</ul>

<h3>Colunas do conjunto de dados:</h3>
<ul>
  <li>Numero Ordem (Número da produção de cada peça)</li>
  <li>Operador (Operador que executou cada etapa)</li>
  <li>Produto (Produto produzido)</li>
  <li>Ocorrência (Um obstáculo na produção)</li>
  <li>Data Inicio (Data de início da produção)</li>
  <li>Hora Inicio (Hora de início da produção)</li>
  <li>Data Fim (Data de fim da produção)</li>
  <li>Hora Fim (Hora de fim da produção)</li>
  <li>Total Horas (Total de horas de cada etapa)</li>
  <li>Qtd Produzida (Unidades produzidas)</li>
  <li>Qtd Rejeitada (Unidades rejeitadas)</li>
</ul>

<h3>Guia de dados:</h3>
<ul>
  <li>"Numero Ordem"</li>
  <ul>
    <li>Ordem crescente</li>
  </ul>
  <li>Horas Trabalhadas</li>
  <ul>
    <li>Nova medida>Horas Trabalhadas = SUM('BaseProdução'[Total Horas])</li>
  </ul>
  <li>Total Produzido</li>
  <ul>
    <li>Nova medida>Total Produzido = SUM('BaseProdução'[Qtd Produzida])</li>
  </ul>
  <li>Total Rejeitado</li>
  <ul>
    <li>Nova medida>Total Rejeitado = SUM('BaseProdução'[Qtd Rejeitada])</li>
  </ul>
  <li>Horas Produtivas</li>
  <ul>
    <li>Soma do total de horas somente se a Ocorrência estiver em branco.</li>
    <li>Nova medida>Horas Produtivas = CALCULATE(SUM('BaseProdução'[Total Horas]), 'BaseProdução'[Ocorrência]=BLANK())</li>
  </ul>
  <li>Horas Paradas</li>
  <ul>
    <li>Nova medida>Horas Paradas = [Horas Trabalhadas] - [Horas Produtivas]</li>
  </ul>
  <li>Produtividade</li>
  <ul>
    <li>Nova medida>% Produtividade = [Horas Produtivas]/[Horas Trabalhadas]</li>
  </ul>
  <li>Qualidade</li>
  <ul>
    <li>Nova medida% Qualidade = [Total Produzido]/([Total Produzido]+[Total Rejeitado])</li>
  </ul>
</ul>

![dashboard-producao](https://github.com/carolinari/PowerBI/assets/85963623/363b5953-6891-454c-a806-80056aef5b6d)








Power BI | DAX | Data Analysis Expressions | Expressões de Análise de Dados
