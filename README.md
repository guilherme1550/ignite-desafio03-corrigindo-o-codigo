<h1 align="center">Ignite Desafio 03 - Corrigindo o código</h1>

<p align="center">
  <a href="#-Projeto">Desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-Tecnologias">Tecnologias</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-Como-executar">Como executar</a>
</p>
<br/>

## 📙 Desafio

Neste desafio, temos uma aplicação em Node.js, onde é necessário analisar o código e realizar as devidas correções para que todos os testes passem. 

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
- id deve ser um uuid válido;
- title é o título do repositório(exemplo: "unform");
- url é a URL que aponta para o repositório(exemplo: "https://github.com/unform/unform");
- techs é um array de string onde é possível guardar o nome de uma tecnologia relacionada ao repositório(exemplo: ["javacript", "nodejs"]);
- likes é quantidade de likes que o repositório recebeu, que será incrementada de 1 em 1 a cada chamada na rota de likes. No momento da criacão de um repositorio, a quantidade de likes sempre será 0;

Não é necessário realizar alterações nos testes, apenas no código que esta no arquivo 📃 index.js.
<br/><br/>

## 🔸 Rotas

### GET `/repositores`

A rota deve retornar uma lista contendo todos os repositórios cadastrados;

### POST `/repositores`

A rota deve receber `title`, `url` e `techs` pelo corpo da requisição e retornar um objeto com as informações do repositório criado e um status `204`.

### PUT `/repositores/:id`

A rota deve receber `title`, `url` e `techs` pelo corpo da requisição e o `id` do repositório que deve ser atualizado pelo parâmetro da rota. Deve alterar apenas as informações recebidas pelo corpo da requisição e retornar esse repositório atualizado.

### DELETE `/repositores/:id`

A rota deve receber, pelo parâmetro da rota, o `id` do repositório que deve ser excluído e retornar um status `204` após a exclusão.

### POST `/repositores/:id/like`

A rota deve receber, pelo parâmetro da rota, o `id` do repositório que deve receber o like e retornar o repositório com a quantidade de likes atualizada.

## 🔸 Testes

- Should be able to create a new repository

Para que esse teste passe, você deve permitir que um novo repositório seja cadastrado pela rota **POST** `/repositories`. Também é necessário que retornar a resposta com o código `201`.

- Should be able to list the projects

Para que esse teste passe, é necessário concluir o teste anterior. Se tudo ocorreu bem, os repositórios cadastrados deverão aparecerem na listagem da rota **GET** `/repositories` e esse teste irá passar.

- Should be able to update repository

Para que esse teste passe, você deve permitir que um repositório seja atualizado a partir de seu id pela rota PUT /repositories/:id usando as informações recebidas pelo corpo da requisição. Lembre-se de manter as informações que não foram passadas pelo corpo, por exemplo:
Se o usuário quiser trocar apenas o title, mantenha url e techs que já estavam no repositório.




## 💻 Tecnologias

Esse projeto foi desenvolvido com as seguintes tecnologias:

- [Express](https://expressjs.com/pt-br/)
- [Jest](https://jestjs.io/)
<br/><br/>



<br/><br/>
## 🔸 Como executar

- Clone o repositório
- Instale as dependências com `yarn`
- Rode os testes com `yarn test`

---

<p align="center">🚀 Desenvolvido durante o bootcamp da Rockeseat Ignite - Trilha Nodejs 🚀<p>