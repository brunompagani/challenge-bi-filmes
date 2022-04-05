# Challenge de BI - Semana 1 (Filmes)

## ACESSE O DASHBOARD [AQUI](https://datastudio.google.com/reporting/774c7382-3039-44a9-9090-cc8d733a175c/page/p_39txjruktc "Projeto Alura Films")

## Habilidades Demonstradas

Atributo | Complexidade
-------- | ------------
Complexidade do Projeto | ⭐️ 
Criação de Dashboards em Google Data Studio | ⭐️ ⭐️ ⭐️ 
Google Sheets | ⭐️ ⭐️ ⭐️ 
Carregamento de Dados | ⭐️ ⭐️ 
Limpeza de dados | ⭐️ ⭐️ 
Transformação de Dados | ⭐️ 
Análise de Dados | ⭐️ 

![picture alt](https://github.com/brunompagani/challenge-bi-filmes/blob/ed49bba3019948a2c7af3ab62c31e9bd2f32cc50/Recursos/diagrama.png)

## Resumo

O Projeto foi proposto pela Alura (escola de tecnologia virtual), como parte do Challenge de BI. Esse é o primeiro de 3 desafios dessa edição.

Realizei esse projeto com o intuito de demonstrar habilidades específicas em criação de dashboards, análise e manipulação de dados. É um projeto simples, mas eficaz no que se propõe. O projeto é para uma empresa fictícia, a Alura Films, que me contratou para fazer uma dashboard a partir de uma base de dados que eles possuem, a base estava em formato “csv”  e consistia em 2 tabelas, uma chamada filmes e outra posters. As ferramentas escolhidas foram o Google Data Studio e o Google Sheets, duas ferramentas amplamente utilizadas que possuem pontos fortes e fracos para cada tipo de trabalho.

## Base de Dados

#### Tableas Fornecidas

A base foi fornecida pela própria empresa, tratada e transformada para facilitar a análise. Os dados foram originalmente extraídos da plataforma IMDB e totalizam 1000 filmes.

#### Web Scraping

Para o cálculo do faturamento ajustado pela inflação foi realizado um web scraping do site do [U.S. BUREAU OF LABOR STATISTICS](https://www.bls.gov/)

#### Principais Vieses da Base

Reconhecer os vieses em uma base de dados é uma habilidade necessária para qualquer um que trabalha com dados, nesse caso os principais vieses percebidos da base são:

- Número Reduzido de Filmes: Apenas 1000 registros
- Filmes mais bem avaliados: A base consiste nos 1000 filmes mais bem avaliados do IMDB, o que não é um problema para analisar os sucessos, mas é um viés importante de se ter em mente.
- Filmes antigos em menor quantidade: Filmes antigos tem menos ocorrências na base, o que trás distorções em médias ou totais de faturamento, por exemplo. De novo para uma análise de dados mais recentes isso não é um problema.

## Google Data Studio

Como meu principal  objetivo com o projeto é demonstrar habilidades em criação de dashboards, a ferramenta na qual faria isso não é o mais relevante, afinal os conceitos no design e análise são o mais importante, dito isso eu escolhi o Data Studio por ser uma ferramenta amplamente utilizada, com muitas funcionalidades, por ser gratuita e de fácil utilização em um sistema Mac OS, o que a torna uma ótima opção comparado com competidores como Power BI e Qlik Sense (não roda em Mac) ou Tableau (versão gratuita possui muitas limitações em conectores).

## Google Sheets

O Google Sheets não é uma ferramenta muito complexa de se trabalhar, principalmente para profissionais de dados, a utilização dela nesse projeto, em vez de um banco relacional, por exemplo, foi simplesmente tirar o foco do carregamento de dados e levar para a manipulação e análise de dados e criação do dashboard. Mesmo assim, para quantidades pequenas de dados ele é uma ótima ferramentas e com ela fui capaz de realizar web scraping para extração de dados e outras transformações na estrutura de dados que facilitaram a leitura pelo Google Data Studio.


## Limpeza e Manipulação de Dados Detalhada

#### Gross (Faturamento Bruto)

Alguns dados de “Gross” (bilheteria) vieram em um formato numérico errado. Os milhares são divididos por vírgula, como num padrão americano, mas alguns dos valores tinham 1 ou dois números no ultimo conjunto de milhares, como em “55,24” e “600,2”, analisando alguns casos específicos percebi que em algum momento na extração original foram perdidos zeros no final, por isso nesses casos eu apenas corrigi os valores. Assim, “55,24” virou “55,240” e “600,2” virou “600,200”. 

#### Faturamento ajustado

Foi realizado um Web Scraping do site do U.S. BUREAU OF LABOR STATISTICS no próprio Google Sheets, onde extraí a inflação acumulada entre todos os anos da base e 2020 (maior ano da Base) e assim calculei o faturamento ajustado no tempo. Dessa maneira pude fornecer uma visão mais justa do faturamento em filmes antigos, comparativamente com os atuais.

#### Runtime (Duração)

Dados vieram no formato “192 min”. Por isso foi criada outra coluna numérica para cálculos, eliminando o “ min”.

#### Genre (Gênero)

A coluna Genre possui de um a três gêneros para cada filme (atributo multi-valorado), dessa forma foi criada uma nova tabela, em formato longo, para facilitar a análise desse atributo.

#### Posters

A tabela de Posters foi juntada com a tabela de Filmes, para facilitar a utilização no Data Studio.

#### Overview (Sinopse)

A coluna Overview foi traduzida automaticamente para o português, para melhorar a leitura desse campo.

#### Certification (Classificação Indicativa)

A Coluna que descreve diversos tipos de classificações indicativas foi usada para construir uma nova coluna, onde é mostrado de forma mais simples os públicos para os quais os filmes são inicialmente indicados, entre crianças, adolescentes e adultos.

#### Stars (Estrelas)

A base de dados trazia as 4 principais estrelas (atores) de cada filme, cada um em uma coluna, por isso eu criei uma novo tabela em formato longo, como eu fiz com a tabela de gêneros.

![picture alt](https://github.com/brunompagani/challenge-bi-filmes/blob/a1ffebc19c8c3c3969ee1953bc83b4f63c4d3d8a/Recursos/pagina_de_diretores.png "Página de diretores")

