---
title: Injeção de dependência e teste unitário
author: Arthur P. Braga
---

#### Observação

*Esse resumo será quebrado em dois, e completado futuramente :)*

----

#### Rascunho

##### Injeção de dependência (DI)
Basicamente diminui o acoplamento de código tornando, não mais necessário, fazer a instância de determinada classe para se utilizar seus métodos. Além de permitir o uso de Mocks em testes unitários.

##### Testes unitários
O teste unitário vai simular a execução de um pequeno pedaço de código, validando a regra do mesmo. Vai validar a relação dos dados parâmetizados e o retorno dos métodos. 

Verify -> Chamada do método - verificar se a chamada está sendo feita de forma correta. Ex: Lançamento em lote, da pra validar a quantidade de vezes que o método foi chamado.

Assert -> Comparação dois valores. Ex: Save de funcionario - se a regra é que nao pode salvar sem ter, por exemplo, o cpf, conseguimos validar se em no cenário em que o cpf é tido como nulo o método está retornando corretamente (uma mensagem de retorno...).

Mockar (simular) -> Simular a dependência, a chamada de métodos, para poder mockar (simular) determinador valores de teste, retornos de métodos... sem nenhuma interatividade com o banco.

O CDI (Contexts and Dependency Injection - Injeção de Dependência e Contextos) é parte integrante do Java, e torna possível o uso de Morcks na aplicação. Ou seja, com o interceptor, é possível simular a chamada e retorno de um método específico, utilizando dados de teste.