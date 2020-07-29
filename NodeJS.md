---
title: NodeJs
author: Arthur P. Braga
---

### What is

Node.js é um interpretador Javascrit fora dos navegadores. *Para Javascript Vanilla cada navegador tem seu interpretador, no caso do Chrome é o V8.* 

Com o Node.js é possível criar aplicações back-end como em Java, PHP... Aplicações desktop, mobile... Não fica restrito apenas à aplicações front-end web;

BRILHANTE - Exige menos recursos computacionais dos servidores (barateando), pois ele utiliza somente uma thread(EventLoop) para tratar as requisições. Sem contar que o EventLoop não espera o retorno das E/S(entrada e saída), ou seja, ele não para de trarar as requisições para esperar as operações serem concluidas(deixando suas aplicações mais rápidas);

Outra vantagem é que ele usa Javascript, ou seja, pode ser usada a mesma linguagem tanto para o front quanto para o back;  

Tem um ecossistema muito grande, ou seja, tem biblioteca para praticamente tudo que você quiser fazer.

---

### General

- Módulos -> É uma forma de se quebrar o código em vários arquivos, organizando-o para que não fique tudo junto em um único grande arquivo. A forma de se utilizar se parece com o instanciamento de classes.
  
  > 1º Precisa exportar as functions que quer utilizar no arquivo principal. 
  > 
  >        module.exports = function ou = {function, function} para mais de uma função;
  > 
  > 2º Depois é só receber essa exportação em uma variável no arquivo principal.
  > 
  >        var nome = requice("local do arquivo");
  > 
  > 3º E Se quiser acessar uma function expecífica -> nome.function;

- Só para lembrar como o node funciona, coloquei esse pequeno código conectando no módulo 'http' do node (o que é bem 'cru', o express é mais robusto) e criando um servidor node usando a porta 8080:

```javascript
var http = require('http');
http.createServer(function (req, res) {
    res.end("<h1>Funfou</h1>");
}).listen(8080);
```

---

### Express and NPM

- O **Express.js** é um framework de desenvolvimento back-end com Node.js. É vantagem usar ele por ser muito mais robusto que o módulo http do node, que só contém o básico para se trabalhar com http.

- O **npm** é o gerenciador de pacotes do node (node package manager). Com ele é possível se utilizar qualquer biblioteca node em seu projeto.

> npm init -> Para iniciar um projeto Node.js e criar o arquivo json com as info do seu projeto.

---

### EJS (Embedded JavaScript templating)

Modelo de Javascript incorporado, é um "motor" de templates(view engine), é responsável por renderizar, exibir HTML nas rotas criadas em Node. 

Além disso ele permite que possamos incorporar JS dentro do HTML, como passar o valor das variáveis, estruturas condicionais, laços de repetição...;

> - Para passar o valor das variáveis no HTML é só passar as variáveis em um objeto no método render do express, e no html.ejs você puxa elas onde quiser com a tag coluna grega <%= var %>
> - Para usar condicionais é tipo no php, coluna grega sem '=' -> ex: <% if(){ %>

---

### Sequelize

É uma biblioteca javascript que permite a manipulação do banco de dados SQL inteiramente por javascript. 

Ex: INSERT INTO user ........        ->        user.create({name: ' ', pwd: ' '........});

```shell
$ npm install --save sequelize
$ npm install --save mysql2 (biblioteca para se trabalhar com mysql usando sequelize)
```

---

### Knex

**Migrations:**

```shell
npx knex migrate:make migration_name
npx knex migrate:latest
```

**Seeds:**

```shell
npx knex seed:make sedd_name
npx knex seed:run
```

---

### Notes

- **Pastas ->** views -> html || public -> arquivos estáticos(img, css...). O express já vai procurar os arquivos respectivos dentro destas pastas, um padrão de nomenclatura já;
- **Partials ->** Reutilização de código html. Igual se faz em php, ou cria componentes em ionic. É só criar um arquivo .ejs colocar seu html dentro (como um navbar...) e chamar nas suas páginas: <%- include ('diretório da partial')%>;
- **Body-Parser ->** Essa biblioteca permite receber os dados codificados de formulários, JSON, XML... e decodifica-los em uma estrutura js, retornando eles em: req.body.;
- **module-alias ->** Pacote para customizar paths no NodeJS. Acaba com './../../../../';
- **bcrypt ->** Biblioteca para encriptamento e criação de hash de senha;
- **Redis ->** Para salvamento de sessões, para não salvar na memória do servidor;
- **Middleware ->** Fica entre a requisição e a resposta, ou seja, podem ser funções que fazem o intermédio entre a requisição e a resposta desejada. Ex: Uma função para verificar se a sessão foi iniciada, se sim ele permite o usuário acessar tal página;
- **SPF ->** Structured Page Fragments
