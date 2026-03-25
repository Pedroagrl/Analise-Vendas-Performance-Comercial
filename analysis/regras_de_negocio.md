# Regras de Negócio e Transformações de Dados

Este documento descreve as principais regras aplicadas na preparação dos dados e construção do modelo no Power BI.

O objetivo foi garantir consistência nos cálculos e permitir análises corretas.

## Organização do Modelo em Esquema Estrela

O modelo foi estruturado seguindo o padrão star schema.

Foi definido que:
- fVendas seria a tabela fato
- As tabelas dimensão filtrariam a fato
- A direção de filtro seria D → F

Isso evita ambiguidade e melhora performance.



## Remoção de Relacionamentos Ambíguos

O modelo original possuía múltiplos caminhos de relacionamento.

Esses relacionamentos foram removidos para evitar erros em medidas e segmentações.

Sempre que possível foi mantido apenas um caminho entre dimensão e fato.



## Criação de Colunas DAX para Relacionamento

Quando não existia chave direta entre tabelas, foram criadas colunas calculadas para permitir o relacionamento correto.

Essa abordagem foi utilizada para manter o modelo consistente sem utilizar muitos-para-muitos.



## Uso da Tabela Calendário

Foi utilizada uma tabela calendário para permitir:

- análise por ano e mês
- cálculo de LY
- cálculo de crescimento

Todas as medidas temporais utilizam essa tabela.


## Implementação de RLS

Foi implementado Row Level Security utilizando a tabela UsuarioRLS.

Cada usuário possui um país associado.

Foi criada uma role que filtra os dados de acordo com o país do usuário.

Isso permite restringir a visualização dos dados por região.


## Uso de Drilldown

Foi utilizado drilldown em gráficos de categoria e produto.

Isso permite:

- manter o visual limpo
- detalhar apenas quando necessário
- melhorar a navegação


## Objetivo das Transformações

As transformações realizadas tiveram como objetivo:

- garantir consistência
- melhorar performance
- evitar erros de cálculo
- permitir análises corretas
- seguir boas práticas de modelagem