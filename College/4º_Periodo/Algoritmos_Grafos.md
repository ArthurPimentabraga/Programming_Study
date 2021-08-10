---
title: Algoritmos em grafos (Puc-Minas - 4º Período)
author: Arthur P. Braga
period: 2/2021
---

# Introdução

Estrutura matemática utilizada para trabalhar com problemas do mundo real.

**Motivação:** Pontes de Konigsberg

Passar por todas as pontes uma única vez e voltar para a área inicial.

<img src="https://upload.wikimedia.org/wikipedia/commons/5/5b/Pontes_K%C3%B6nigsberg.JPG" style="width:55%">

**Motivação:** Algoritmos em grafo podem ser utilizados em redes sociais, jogos, engenharia... Como por exemplo:

- Transporte aéreo (Objeto: cidades, Relacionamento: vôo comercial entre duas cidades);
- GPS para definir o menor caminho;
- Entre outros.

---

# Definições

05/08 :watch:

Grafo é uma estrutura abstrata que representa um conjunto de elementos denominados vértices (v) e suas relações de interdependências entre eles, ou chamados de arestas (e).

> Exemplo: Vértice: Cidades - Arestas: Rodovias entre as cidades

**G = (V,E)**   -   V = { A,B,C,D}   -   E = { (A;B);(A;D);(C;D) }

> Note: Programar um vértice (objeto - classe)

- A **ordem** de um grafo G é a cardinalidade (nº de elementos) de V 
- O **tamanho** de um grafo G é a cardinalidade de E

#### Grafo valorado / ponderado

É dito valorado se existem **valores** associados aos vértices ou arestas desse grafo. Tais valores são denominados **pesos**.

Exemplo: Custo de se movimentar entre dois pontos.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/grafo-valorado.png" style="width:30%">

#### Grafo não direcionado / não orientado

Por padrão, duas arestas são consideradas a mesma. Ou seja, não possui direção obrigatória definida, seu sentido não é importante. 

#### Grafo direcionado / orientado / digrafo

Agora o sentido da aresta importa e é marcado por uma seta. Seu sentido é importante, pois pode ter significados diferentes. 

> Exemplo: Linha de montagem, um processo só pode executar após o término de outra.

Pode ter correspondencia em ambos os sentidos, porém nesse caso teríamos que ter **duas arestas**.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/grafo-direcionado.png" style="width:40%">

#### Laço (Loop)

Aresta que liga um vértice a si mesmo.

#### Arestas paralelas

Duas ou mais arestas associadas ao mesmo par de vértices.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/arestas-paralelas.png" style="width:40%">

#### Grafo simples

Não possui nem arestas paralelas nem laços.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/grafo-simples.png" style="width:30%">

#### Vértices adjacentes (vizinhos)

Dois vértices são ditos adjacentes se existe uma aresta que os liga, logos esses vértices serão vizinhos/adjacentes.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/vertices_adjacentes.png" style="width:70%">

#### Vértices sucessores e antecessores

Somente em **grafos direcionados**!

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/sucessores_antecessores.png" style="width:70%">

#### Incidência 

Quando um vértice Vi é o vértice final de alguma aresta Ei, Vi e Ei são incidentes.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/incidencia.png" style="width:30%">

#### Arestas adjacentes

Duas arestas *não paralelas* compartilhando um vértice.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/arestas_adjacentes.png" style="width:30%">

#### Grau de um vértice (d)

Em um grafo *não direcionado*, o grau de um vértice é igual ao nº de arestas incidentes no vértice.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/grau_vertice.png" style="width:50%">

- Vértices com grau 0 são chamados **isolados.**
- Grafos que possuem somente vértices isolados são chamados de **grafos nulos.**
- Vértice de grau 1 é chamado de **pendente.**
- Um laço conta como duas arestas!

#### Teorema 1

A soma dos graus de todos os vértices de um grafo G é duas vezes o nº de arestas de G.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/Teorema1.png" style="width:40%">

> Ao contar os graus dos vértices, contamos cada extremidade de arestas uma vez. como cada aresta tem duas extremidades, cada aresta foi contada duas vezes.

#### Teorema 2

O nº de vértices de grau ímpar em um grafo é sempre **par**.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/Teorema2.png" style="width:55%">

#### Passeio em um grafo

Um passeio entre os vértices 1 e 2 é uma sequência alternada de vértices e arestas que começa no vértice 1 e termina no vértice 2 . 

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/passeio.png" style="width:55%">

> Poderíamos pensar que apenas a ordem dos nós é importante, porém podemos ter passeios diferentes com a mesma sequência de vértices.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/passeio2.png" style="width:65%">

#### Caminho em um grafo

Um caminho é um passeio sem vértice repetido. Exemplo: Caminhos entre os vértices 1 e 4:

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/caminhos.png" style="width:60%">

#### Grafo regular

Todos os vértices tem o mesmo grau.

#### Grafo completo

Para cada par de vértices existe uma aresta entre eles. Consequentemente, quaisquer dois vértices distintos são adjacentes (vizinhos).

> Note: Um grafo completo com n vértices é dito: Kn 

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/grafo_completo.png" style="width:60%">

> Como achar o grau dos vértices -> n-1
>
> Como achar o nº de arestas -> (d * n) / 2

#### Grafo conexo

Existe pelo menos um caminho entre todos os pares de vértices, ou seja, se sai de um vértice, consegue chegar em qualquer outro.

#### Grafo desconexo

Consiste de dois ou mais grafos conexos. Cada um dos *subgrafos* conexos é chamado de *componente.*

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/grafo_desconexo.png" style="width:40%">

---

