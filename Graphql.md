## Grphql

- Cada módulo que quer adicionar ou extender de um GraphQL scheme basta colocar um arquivo scheme.graphql no seu diretório etc. 
- Exemplo o módulo CustomerGraphQl adiciona uma **query** e **varias mutations** ao **endpoint graphql para visualizar e modificar os dados do cliente**
- O módulo CustomerGraphQL depende do módulo principal Customer.
- Um arquivo scheme.graphql de um módulo GraphQL **define como os atributos do módulo podem ser usados em queries e mutations** graphql
- O arquivo scheme.graphqls define as queries, mutations, interfaces e os tipos de dados de todos os atributos. 
No scheme.graphqls: 
- Define a estrutura de consultas e multações
- Determina quais atributos podem ser usados para entrada e saída em queries e mutations do GraphQL. As solicitações e respostas contêm listas separadas de atributos válidos.
- Aponta para resolvers que verificam e processam os dados de entrada e resposta
- Serve como font para exibir o scheme em um graphql browser??
- Define quais objetos são armazenados em cache.
- No geral define a estrutura básica das queries e mutations. 

## output attributes

- os atributos de saída são definidos em interfaces
- page_info: Um objeto que inclui os valores page_info e currentPage especificados na consulta
- total_count: Total de itens
- Items: Uma matriz de produtos que correspondem aos critérios de pesquisa especificados


