# Decisões Analíticas do Projeto

Este projeto foi desenvolvido com o objetivo de praticar modelagem de dados, criação de medidas em DAX e construção de dashboards analíticos no Power BI, utilizando um conjunto de dados de vendas contendo informações sobre produtos, promoções, lojas e períodos de tempo.

Durante o desenvolvimento foram aplicadas boas práticas de modelagem, organização visual e definição de indicadores, com foco em simular um cenário real de análise comercial.


## Separação dos Dashboards

O dashboard foi dividido em duas páginas principais:

1. Visão Geral de Vendas  
2. Análise de Produtos e Promoções  

A primeira página apresenta indicadores executivos e visão geral do desempenho, enquanto a segunda página permite análise mais detalhada por produto, categoria e promoção.

Essa separação foi adotada para reduzir sobrecarga visual e facilitar a navegação entre análises gerais e análises detalhadas.


## Modelagem em Esquema Estrela

O modelo foi reorganizado seguindo o padrão de esquema estrela, utilizando a tabela fato de vendas como centro do modelo e conectando as tabelas dimensão ao redor.

Foram utilizadas as seguintes dimensões:

- Calendário  
- Produtos  
- Categorias  
- Promoções  
- Lojas  
- Localidades  

A direção de filtro foi definida das dimensões para a tabela fato (D → F), garantindo que os cálculos fossem realizados corretamente.

Relacionamentos ambíguos foram removidos para evitar resultados incorretos em medidas e segmentações.


## Criação de Colunas Auxiliares para Relacionamentos

Em alguns casos não existia uma chave direta para relacionamento entre tabelas.

Para resolver isso, foram criadas colunas utilizando DAX para permitir a ligação correta entre dimensões e tabela fato, mantendo o modelo consistente.

Essa abordagem foi utilizada para manter o padrão estrela e evitar relacionamentos muitos-para-muitos.


## Definição dos Indicadores

Os indicadores foram definidos com foco em análise de performance comercial, incluindo:

- Vendas totais  
- Vendas líquidas  
- Margem  
- Percentual de desconto  
- Crescimento em relação ao ano anterior  
- Ranking de produtos  
- Impacto das promoções  

O objetivo foi permitir avaliar tendência, desempenho e resultado das campanhas.


## Uso de Drilldown e Navegação Hierárquica

Nos gráficos de categoria e produto foi utilizado drilldown, permitindo navegar da categoria para o produto.

Esse recurso foi aplicado para manter o dashboard limpo, evitando excesso de informações na visualização principal.


## Organização Visual

Foi utilizado layout personalizado com background externo para melhorar a organização visual.

Os gráficos foram distribuídos para responder perguntas como:

- Como as vendas evoluíram ao longo do tempo  
- Quais categorias vendem mais  
- Qual o impacto das promoções  
- Quais produtos possuem melhor desempenho  
