---
title: Code injection
author: Pedro Henrique Faria Andrade
---

# Code injection

Code injection, injeção de código em português, é um termo utilizado para a prática de injetar códigos maliciosos em aplicativos web. Esse tipo de ataque explora falhas em validações de entradas / saídas, como por exemplo o manuseio inadequado de dados não confiáveis. Tal prática se limita a funções de uma linguagem específica, ou seja, apenas a linguagem utilizada e não um aproveitamento total do código (command injection => contexto shell).

### Alguns exemplos de code injection:

- Code Injection com linguagem (que tenha a possibilidade de executar ao lado do servidor): o invasor injeta um código que será interpretado e executado em seu servidor. No qual suas principais falhas são validações de entradas, inclusão de entradas não confiáveis. Com isso o invasor pode listar diretórios, deletar arquivos, roubar dados sensíveis, etc... Uma das linguagens mais usadas para a injeção de código é o PHP, com o auxílio de funções como a eval (que funciona como um parse), entre outros.
- SQL Injection: quando um aplicativo utiliza um banco de dados e não faz tratamento de seus inputs. Podendo abrir espaços para o invasor acessar o aplicativo mesmo não tendo o acesso, leitura e/ou armazenamento de dados, deletar tabelas, etc. Nesse tipo de injeção a postura tomada pelos invasores é que onde pedir entradas de usuários faz com que a query sempre retorne um valor positivo, como por exemplo, 1 = 1.
- XSS (cross-site scripting): é um tipo de injeção de códigos por meio de campos de texto de uma página já existente em seu alvo, simulando uma página que não deveria existir. Como por exemplo um formulário para pegar os dados de um usuário que for acessar a essa página. Para ter segurança e evitar tal tipo de injeção, alguns browsers possuem.
- XML: esse tipo de injeção é bem parecido com o XSS, porém nesse tipo de ataque o invasor utiliza a XML que é uma linguagem de marcação.

- Injeção de log: essa injeção é bastante utilizada como disfarce para outros ataques, por ser algo que desenvolvedores não se atém tanto. Esse tipo de ataque é possível pois muitos aplicativos usam algum log para registro de históricos de eventos, coleta de dados, entre outros. E com isso abre uma oportunidade do invasor injetar códigos ou dados falsos nesses logs. Um exemplo desse tipo de injeção em ação é por meio de inúmeras tentativas de login de usuário serem mal sucedido, gerando um log muitas vezes com uma mensagem de falha ao fazer o login. A partir disso o invasor injeta (forja) um log de login bem sucedido, neutralizando o sistema de login do aplicativo.

### Como prevenir o code injection ?

- Validando entradas: procure caracteres de escape(possuem “/” alinhados a ele) e outros símbolos especiais para, como marcas de comentário, caracteres de terminação de linha e delimitadores de comando.
- Limitar funcionalidades ao usuário, evitando escalabilidade em uma injeção
- Boa configuração da aplicação, pois como podemos perceber os ataques podem vir de diversos lugares.
- Utilização de ferramentas e scanners que auxiliam a encontrar vulnerabilidades em sua aplicação.