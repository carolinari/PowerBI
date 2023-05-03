<h1>Dashboard Vendas</h1>

Dataset: Base Vendas.xlsx

<h3>Dashboard com:</h3>
<ul>
  <li>Faturamento total</li>
  <li>Quantidade vendida</li>
  <li>Produto mais vendido</li>
  <li>Faturamento por produto</li>
  <li>Faturamento por mês</li>
  <li>Quantidade vendida por gênero</li>
  <li>Faturamento por estado</li>
</ul>

<h3>Colunas do conjunto de dados inicialmente:</h3>
<ul>
  <li>SKU (código do produto vendido)</li>
  <li>Produto</li>
  <li>Qtd Vendida</li>
  <li>Data</li>
  <li>Loja</li>
  <li>Preço Unitário</li>
  <li>Nome</li>
  <li>Sobrenome</li>
  <li>Gênero</li>
</ul>

<h3>Transformar dados (Power Query):</h3>
<ul>
  <li>Remover "Column10" porque está vazia</li>
  <li>Remover linhas em Branco - Página inicial>Reduzir linhas>Remover linhas em Branco</li>
  <li>Juntar colunas "Nome" e "Sobrenome" - Transformar>Mesclar Coluna>Separador "Espaço" e Novo nome "Nome Completo"</li>
  <li>Separar cidade de estado da coluna "Loja" - Transformar>Dividir coluna>Por delimitador>" - "</li>
  <li>Renomear colunas "Loja 1" e "Loja 2" para "Cidade" e "Estado"</li>
  <li>Editar coluna "Gênero" - Substituir "M" por "Masculino" e "F" por "Feminino" - Transformar>Substituir valores</li>
  <li>Adicionar uma nova coluna "Faturamento" (Qtd Vendida x Preço Unitário) - Adicionar coluna>Padrão>Multiplicar</li>
  <li>Renomear coluna "Multiplicação" para "Faturamento"</li>
</ul>

<h3>No Power BI - Exibição de dados:</h3>
<ul>
  <li>Data - Classificar em ordem crescente</li>
</ul>

