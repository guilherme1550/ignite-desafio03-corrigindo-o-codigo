<h1 align="center">Ignite Desafio 03 - Corrigindo o código</h1>

<p align="center">
  <a href="#-Projeto">Desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-Rotas">Rotas</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-Testes-de-repositórios">Testes de repositórios</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-Testes-de-likes">Testes de likes</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-Tecnologias">Tecnologias</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-Como-executar">Como executar</a>
</p>
<br/>

## 📙 Desafio

Neste desafio, temos uma aplicação em Node.js, onde foi necessário analisar o código e realizar as devidas correções para que fossem possível passarem todos os testes . 

Esta aplicacão realiza o CRUD(Create, Read, Update, Delete) de repósitorios de projeto. Sendo possível dar likes em cada repositórios, aumentando a quantidade de 1 em 1, cada vez que a rota é chamada.

Estrutura de um repositório a ser criado:

`
{
  id: uuid(),
  title,
  url,
  techs,
  likes: 0
}
`

Descricão de cada propriedade:
- id é um uuid;
- title é o título do repositório(exemplo: "unform");
- url é a URL que aponta para o repositório(exemplo: "https://github.com/unform/unform");
- techs é um array de string onde é possível guardar o nome de uma tecnologia relacionada ao repositório(exemplo: ["javacript", "nodejs"]);
- likes é quantidade de likes que o repositório recebeu, que será incrementada de 1 em 1 a cada chamada na rota de likes. No momento da criacão de um repositorio, a quantidade de likes sempre será 0;

Não foi necessário realizar alterações nos testes, apenas no código que esta no arquivo 📃 index.js.
<br/><br/>

## 🔸 Rotas

### GET `/repositores`

A rota retorna uma lista contendo todos os repositórios cadastrados;

### POST `/repositores`

A rota recebe `title`, `url` e `techs` pelo corpo da requisição e retorna um objeto com as informações do repositório criado e um status `201`.

### PUT `/repositores/:id`

A rota recebe `title`, `url` e `techs` pelo corpo da requisição e o `id` do repositório que deve ser atualizado pelo parâmetro da rota. Altera apenas as informações recebidas pelo corpo da requisição e retorna esse repositório atualizado.

### DELETE `/repositores/:id`

A rota recebe, pelo parâmetro da rota, o `id` do repositório que deve ser excluído e retorna um status `204` após a exclusão.

### POST `/repositores/:id/like`

A rota recebe, pelo parâmetro da rota, o `id` do repositório que deve receber o like e retorna o repositório com a quantidade de likes atualizada.
<br/><br/>

## 🔸 Testes de repositórios

- Should be able to create a new repository

Para que esse teste passe, deve-se permitir que um novo repositório seja cadastrado pela rota **POST** `/repositories`. Também é necessário que retorne a resposta com o código `201`.

- Should be able to list the projects

Para que esse teste passe, é necessário concluir o teste anterior. Se tudo ocorreu bem, os repositórios cadastrados deverão aparecer na listagem da rota **GET** `/repositories` e esse teste irá passar.

- Should be able to update repository

Para que esse teste passe, deve-se permitir que um repositório seja atualizado a partir de seu `id` pela rota **PUT** `/repositories/:id` usando as informações recebidas pelo corpo da requisição. As informações que não foram passadas pelo corpo devem ser mantidas, por exemplo:
Se o usuário quiser trocar apenas o `title`, será mantido a `url` e `techs` que já estavam no repositório.

- Should not be able to update a non existing repository

Para que esse teste passe, deve-se verificar se o repositório existe antes de atualizar as informações na rota **PUT** `/repositories/:id`. Caso não exista, é retornado um status `404` (que é o status para Not Found) com uma mensagem de erro no formato `{ error: "Mensagem do erro" }`.

- Should not be able to update repository likes manually

Para que esse teste passe, deve-se impedir que a quantidade de likes de um repositório seja alterada manualmente através da rota **PUT** `/repositories/:id`.

- Should be able to delete the repository

Para que esse teste passe, deve-se permitir que um repositório seja excluído através do `id` passado pela rota **DELETE** `/repositories/:id`.

- Should not be able to delete a non existing repository

Para que esse teste passe, deve-se validar se o repositório existe antes de excluí-lo. Caso o repositório não exista, é retornado um status `404` com uma mensagem de erro no formato `{ error: "Mensagem do erro" }`.
<br/><br/>

## 🔸 Testes de likes

- Should be able to give a like to the repository

Para que esse teste passe, deve ser possível incrementar a quantidade de likes em `1` a cada chamada na rota **POST** `/repositories/:id/like`. É utilizado o `id` passado por parâmetro na rota para realizar essa ação.

- Should not be able to give a like to a non existing repository

Para que esse teste passe, deve-se validar que um repositório existe antes de incrementar a quantidade de likes. Caso não exista, é retornado um status `404` com uma mensagem de erro no formato `{ error: "Mensagem do erro" }`.
<br/><br/>

## 💻 Tecnologias

Essa aplicacão foi desenvolvido com as seguintes tecnologias:

- [Express](https://expressjs.com/pt-br/)
- [Jest](https://jestjs.io/)
<br/><br/>

## 🔸 Como executar

- Clone o repositório
- Instale as dependências com `yarn`
- Rode os testes com `yarn test`

---

<p align="center">🚀 Desenvolvido durante o bootcamp da Rockeseat Ignite - Trilha Nodejs 🚀<p>