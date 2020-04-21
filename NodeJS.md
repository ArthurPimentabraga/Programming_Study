---
title: NodeJs
author: Arthur P. Braga
---

### What is

- Node.js é um interpretador Javascrit fora dos navegadores. *Para Javascript Vanilla cada navegador tem seu interpretador, no caso do Chrome é o V8.* 
  
  
  
- Com o Node.js é possível criar aplicações back-end como em Java, PHP... Aplicações desktop, mobile... Não fica restrito apenas à aplicações front-end web;
  
  
  
- BRILHANTE - Exige menos recursos computacionais dos servidores (barateando), pois ele utiliza somente uma thread(EventLoop) para tratar as requisições. Sem contar que o EventLoop não espera o retorno das E/S(entrada e saída), ou seja, ele não para de trarar as requisições para esperar as operações serem concluidas(deixando suas aplicações mais rápidas);

  

- Outra vantagem é que ele usa Javascript, ou seja, pode ser usada a mesma linguagem tanto para o front quanto para o back;  

  

- Tem um ecossistema muito grande, ou seja, tem biblioteca para praticamente tudo que você quiser fazer.

### General

- Módulos -> É uma forma de se quebrar o código em vários arquivos, organizando-o para que não fique tudo junto em um único grande arquivo. A forma de se utilizar se parece com o instanciamento de classes.
>1º Precisa exportar as functions que quer utilizar no arquivo principal. 
>		module.exports = function ou = {function, function} para mais de uma função;
>2º Depois é só receber essa exportação em uma variável no arquivo principal.
>		var nome = requice("local do arquivo");
>3º E Se quiser acessar uma function expecífica -> nome.function;

