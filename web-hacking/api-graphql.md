# API GraphQL

API GraphQL permite consultas flexíveis e eficientes a dados, mas pode ser vulnerável a falhas como exposição de esquemas ou falta de validação.

**Identificar erro em GraphQL**

"GET query missing"



Podemos enviar querys para o backend&#x20;

?query=



Graphql client

{% code overflow="wrap" %}
```graphql
{"query":"query IntrospectionQuery{__schema{queryType{name}mutationType{name}subscriptionType{name}types{...FullType}directives{name description locations args{...InputValue}}}}fragment FullType on __Type{kind name description fields(includeDeprecated:true){name description args{...InputValue}type{...TypeRef}isDeprecated deprecationReason}inputFields{...InputValue}interfaces{...TypeRef}enumValues(includeDeprecated:true){name description isDeprecated deprecationReason}possibleTypes{...TypeRef}}fragment InputValue on __InputValue{name description type{...TypeRef}defaultValue}fragment TypeRef on __Type{kind name ofType{kind name ofType{kind name ofType{kind name ofType{kind name ofType{kind name ofType{kind name ofType{kind name}}}}}}}}"}
```
{% endcode %}



query {users{id, name, password\}}







{% embed url="https://graphql.org/learn/introspection/" %}

{% @github-files/github-code-block url="https://github.com/graphql-kit/graphql-voyager" %}

{% embed url="https://graphql-kit.com/graphql-voyager/" %}













