# graphql 기초 배우기

- types, schema, queries, mutations
- 패키지: NodeJS, GraphQL, Apollo, GraphiQL

## API 란?

- Application Programming Interface 의 약자를 의미한다.
- tv리모컨이 tv제작자가 사용자에게 tv를 조작할수 있도록 버튼을 노출시킨 기계인 것처럼, API 도 개발자가 사용자에게 기능을 수행할 수 있도록 버튼을 노출시킨 것이다.

## REST api

- REST api 와 Graphql api 차이점은 이 버튼들이 어떻게 노출되어 있는지에 있다.
- REST api 는 서버에 요청을 할때 URL 로 통신이 이루어진다.
- REST api 는 수많은 디바이스들이 URL로 요청을 보낼 수 있기 때문에 범용적으로 쓸 수 있다.
- URL 에 의미를 담을 수 있고 사람들은 비슷한 컨벤션을 사용하기 때문에 이해하고 사용하기도 쉽다.
- HTTP 메서드랑 REST api 와 조합을 이루면 더욱 강력해진다.

## REST + HTTP

- URL 만으로 모든 것을 하는게 아니다.
- `api/movies/create` 와 같은 방식으로 URL 에 동사를 넣는 것은 적절하지 않다. 왜냐면 직관적이지 않고 어떤 동사를 써야 하는지 일일이 확인해야되기 때문.
- REST 와 HTTP 메서드를 결합해서 URL 이 더 많은 작업을 할 수 있게 한다.
- GET / POST / PUT / DELETE / PATCH

<hr>

## GraphQL

- GraphQL 은 REST api 가 가진 문제점을 해결하기 위해 나왔다
- GraphQl 은 뭘 해야하고 뭘 하면 안되는지 등을 정리한 specification 이다.
- 사람들은 specification 을 읽고 그것을 다룰 수 있는 코드를 짠다.(ex graphql-js)

## REST api 의 문제점

1. Over-fetching : 내가 데이터를 실제로 쓰는 것보다 더 많은 데이터를 받는 것을 의미한다. 그래서 서버나 db는 필요한 일보다 더 많은 일을 하게 되고 비용을 발생시킨다.

2. Under-fetching : 우리가 필요한 것보다 덜 받아서 추가적으로 여러가지 요청을 해야 된다.

## graphQl api

- 한번의 로딩으로 필요한 데이터를 모두 받을 수 있다.
- `graphql.org/swapi-graphql` 에서 graphql 을 연습해볼 수 있다.

## Apollo 서버로 grphQl api 만들기

> Apollo 서버는 graphql 을 이해하는 서버이다. (graphql specification 을 따른다)

- Apollo 서버만 있어도 node.js 서버처럼 작동한다.
- express, fastfy, hapi, coa 등 어떤 node.js BE 라도 Apollo 서버를 최상단에 추가할 수 있다
  - node.js 로 만든 rest api 서버가 있을 떄, graphql api 로 바꾸고 싶다면 middleware 만 추가하면 된다.

### 세팅

1. `mkdir graphql-tutorial-tweetql`
2. `code graphql-tutorial-tweetql`
3. `npm init -y`
4. `npm i apollo-server graphql` graphql 과 apollo-server 설치
5. `npm i nodemon -D` : 더 나은 개발환경
6. `server.js` 와 `.gitignore` 파일을 만든다 : .gitignore 파일에 `node_modules/` 추가
7. `git init` 깃 초기화
8. `package.json` 에서 `"type": "module"` 추가 scripts 에는 `"start": "nodemon server.js"` 추가

> Apollo server는 schema 나 modules 또는 typeDefs 가 있어야 된다.
