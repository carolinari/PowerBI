<h1>Dashboard de RH</h1>

Conjunto de dados: BaseFuncionarios.xlsx

<h3>Dashboard com:</h3>
<ul>
  <li>Contratações</li>
  <li>Funcionários Ativos</li>
  <li>Demissões</li>
  <li>Turnover</li>
  <li>Contratações por Ano</li>
  <li>Funcionários por Cidade</li>
  <li>Funcionários por Gênero</li>
  <li>Funcionários por Área e Cargo</li>
</ul>

<h4>Dashboard - Tooltip - Em gráfico de Funcionários por Cidade:</h4>
<ul>
  <li>Funcionários Ativos</li>
  <li>Salário Total</li>
  <li>Horas Extras por Cargo</li>
</ul>

<h3>Colunas do conjunto de dados:</h3>
<ul>
  <li>ID RH</li>
  <li>Nome Completo</li>
  <li>Estado Civil</li>
  <li>Gênero</li>
  <li>Endereço</li>
  <li>Data de Contratação</li>
  <li>Data de Demissão</li>
  <li>Data de Nascimento</li>
  <li>Salário</li>
  <li>Avaliação do Funcionário</li>
  <li>Cargo</li>
  <li>Horas Extras</li>
  <li>Área</li>
</ul>

<h3>Transformar dados:</h3>
<ul>
  <li>Remover linhas em branco</li>
  <ul>
  <li>Página Inicial > Remover Linhas > Remover Linhas em Branco</li>
  </ul>
  <li>Coluna "Ano" - Ano da contratação de cada funcionário</li>
  <ul>
  <li>Coluna "Data de Contratação" > Guia "Adicionar Coluna" > Data > Ano > Ano</li>
  </ul>
  <li>Coluna "Cidade" - Cidade de cada funcionário</li>
  <ul>
  <li>Coluna "Endereço" > Guia "Adicionar Coluna" > Coluna de Exemplos > Da Seleção</li>
  <li>Digitar exemplos das cidades para que o Power Query identifique o padrão</li>
  <li>Renomear coluna para "Cidade"</li>
  </ul>
</ul>

<h3>Medidas criadas:</h3>
<ul>
  <li>Total Contratacoes - Total de contratações (atuais e demitidos)</li>
  <ul>
  <li>Contagem do total de linhas.</li>
  <li>Nova medida > Total Contratacoes = COUNTROWS(Plan1)</li>
  </ul>
  <li>Funcionários - Funcionários atuais</li>
  <ul>
  <li>Contagem das linhas em que a data de demissão está em branco.</li>
  <li>Nova medida > Funcionários = CALCULATE(COUNTROWS(Plan1), Plan1[Data de Demissao]=BLANK())</li>
  </ul>
  <li>Demissoes - Funcionários demitidos</li>
  <ul>
  <li>Contagem das linhas com a "data de demissão" preenchida.</li>
  <li>Nova medida > Demissoes = CALCULATE(COUNTROWS(Plan1), Plan1[Data de Demissao]<>BLANK())</li>
  </ul>
  <li>% Turnover</li>
  <ul>
  <li>Percentual de demissões em relação as contratações atuais.</li>
  <li>Nova medida > % Turnover = [Demissoes]/[Total Contratacoes]</li>
  <li>Ferramentas de Medida > Formato percentual</li>
  </ul>
</ul>









Power BI | DAX | Data Analysis Expressions | Expressões de Análise de Dados
