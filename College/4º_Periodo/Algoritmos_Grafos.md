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

> *Arestas paralelas contam também!*

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

# Representação e Operações

10/08 :watch:

Como representar um grafo em um algoritmo, em uma estrutura de dados?

Principais estruturas:

- Matriz de adjacência;
- Lista de adjacência;
- Matriz de incidência.

## Matriz de adjacência

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/metriz-adjacencia.png" style="width:60%">

> Se as arestas tiverem pesos (grafo valorado), suas posições na matriz poderiam ter os valores respectivos.

Em um **grafo direcionado** a posição na matriz só recebe valor no vértice "de chegada".

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/matriz_grafo_direcionado.png" style="width:60%">

## Lista de adjacência

Como se fosse uma hash, uma lista de vetores, e cada vetor tem uma lista de adjacências. Ou seja, cada elemento do vetor contém dois campos: a identificação de um vértice e um ponteiro para uma lista encadeada contendo os **vizinhos** do vértice correspondente.

> - Cada vértice é um elemento de uma lista ;
> - Cada vértice contém uma lista de arestas, indicando o outro par que a compõe.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/lista_Adjacencia.png" style="width:80%">

Grafos não direcionados também podem ser representados por uma lista de adjacência, só criar a sublista com todos os vetores vizinhos de cada vértice.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/list_adjacencia_2.png" style="width:80%">

## Matriz de incidência

- Índice = +1, se a aresta tem **origem** no vértice i;
- Índice = -1, se i é o vértice **destino** da aresta;
- Índice = 0, se a aresta **não incide** no vértice i.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/matriz_incidencia.png" style="width:60%">

>  Em um grafo **não direcionado** a gente só marca os vértices de incidência e origem, com 0 ou 1.

## Isomorfismo

Grafos "idênticos" em relação ao nº de arestas, vértices, graus e nº de componentes. Porém só isso não basta, para o grafo ser isomorfo a relação de incidência precisa ser preservada.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/isomorfismo.png" style="width:80%">

Grafos que possuam todas as características menos a preservação de incidência:

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/grafos_nao_isomorfos.png" style="width:60%">

Observe que é necessário associar o vértice X do grafo G ao vértice Y do grafo H, pois não existe nenhum outro vértice com grau 3 em H. Mas o vértice Y é adjacente a apenas um vértice de grau 1, enquanto que X em G é adjacente a dois vértices de grau 1.

## Grafo complementar

Um grafo é complementar de outro quando:

- Todos os vértices de C(G) são todos os vértices de G;
- E as arestas de C(G) são exatamente as arestas que faltam em G para formarmos um grafo completo.

> Arestas do grafo G não vão fazer parte do C(G), ou seja, C(G) é um grafo que contém todas as arestas faltantes para G ser um grafo completo. 

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/grafo_complementar.png" style="width:60%">

## Subgrafos

12/08 :watch:

Um grafo H é dito ser um *subgrafo* de um grafo G se todos os vértices e todas as arestas de H estão em G.

- Todo grafo é subgrafo de si próprio;
- O subgrafo de um subgrafo de G é subgrafo de G;
- Um vértice simples de G é um subgrafo de G;
- Uma aresta simples de G (com suas extremidades) é subgrafo de G.

### Subgrafos induzidos por arestas

Um subgrafo obtido por um subconjunto de arestas (e seus respectivos vértices).

Ex.: Mapear e manter somente as lanchonetes cuja distância é < 1km.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/subgrafo_aresta.png" style="width:60%">

### Subgrafos induzidos por vértices

Subgrafo obtido por um subconjunto de vértices (e suas respectivas arestas). 

Exemplo: Manter somente os times que tem características em comum.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/subgrafo_vertice.png" style="width:60%">

### Subgrafos disjuntos de arestas

Dois (ou mais) subgrafos de G são disjuntos de arestas se ambos não tiverem arestas em comum.

### Subgrafos disjuntos de vértices

Dois (ou mais) subgrafos de G são disjuntos de vértices se ambos não tiverem vértices em comum.

## Operações

### União e Soma

- União: Considerando dois grafos distintos, a união G1 ∪ G2 é formada pelo grafo que contém o conjunto de vértices V1 e V2, e o conjunto de arestas E1 e E2. Ou seja, basicamente dois grafos são considerados um.
  - G: Vg= {1, 2}; Eg= {(1, 2)} 
  - H: Vh= {3, 4}; Eh= { } 
  - G ∪ H: Vg∪h = {1, 2, 3, 4}; Eg∪h = {(1, 2)}
- Soma: É a união com todos os vértices de G1 vão ter arestas ligando a todos os vértices de G2.
  - G: Vg= {1, 2}; Eg = {(1, 2)} 
  - H: Vh = {3, 4}; Eh = { } 
  - G + H: Vg+h = {1, 2, 3, 4};  Eg+h = {(1, 2), (1, 3), (1, 4), (2, 3), (2, 4)}

<img src="https://slideplayer.com.br/slide/1732957/7/images/3/Exemplo+1+2+G+H+3+4+G+%EF%83%88+H+G+%2B+H.jpg" style="width:60%">

### Interseção

Resulta em um grafo formado pela interseção das arestas e vértices, ou seja, só aqueles cujo ambos tenham. Ex.:

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/intersecao.png" style="width:70%">

### Ring sum

Basicamente é a união de dois grafos sem incluir a interseção. Ex.:

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/ringSum.png" style="width:75%">

### Remoção de aresta e vértice

- **Remoção de aresta:** Se e é uma aresta de um grafo G, denota-se G-e o grafo obtidop pela remoção da aresta e de G.
- **Remoção de vérice:** Mesma ideia, porém além de retirar o vértice, é necessário retirar todas as arestas incidentes nele.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/remocao_aresta.png" style="width:60%">

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/remocao_vertice.png" style="width:60%">

### Contração de aresta

Retirar uma aresta desejada e unir os dois vértices incidentes nela.

> Denota-se por **G/e** o grafo obtido pela contração da aresta *e*. Significa remover *e* de G e unir suas duas extremidades v, w de tal modo que o vértice resultante seja incidente às arestas originalmente incidentes a v e w.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/contracao_aresta.png" style="width:60%">

### Propriedades

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/propriedades_Operacoes.png" style="width:50%">

### Grafo transposto

Seja um grafo direcionado (apenas direcionados) G = (V, E), seu grafo transposto Gt = (V, E1), cujo todas as arestas tem sentido oposto.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/transposto.png" style="width:70%">

### Grafo bipartido

É um grafo não orientado que pode ser dividido em dois subconjuntos de vértices, cujo não possuem arestas ligando dois vértices do mesmo subconjunto.

- Se diz bipartido um grafo G de tipo (p, q) se for um grafo simples de ordem p+q;

Temos também o **grafo bipartido completo**, nada mais é que um grafo bipartido tal que cada vértice de um subconjunto está associado a cada vértice do outro subconjunto.

> O grafo bipartido completo com partições de tamanho |V1| = m e |V2| = n é chamado Km,n.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/bipartido.png" style="width:60%">

#### Teorema

Um grafo é bipartido se, e somente se, todo ciclo de G possuir comprimento par.

> Obs: Ciclo -> Todo caminho cujo vértice inicial e final são os mesmos sem repetição de vértice, ou seja, sai e volta pro mesmo vértice sem repetir nenhum a não ser o inicial.

---

# Caminhos e Circuitos - Parte 1-2

17/08 :watch:

> Vale lembrar os conceitos de:
>
> - Passeio
> - Caminho
>   - **Caminho aberto:** Vértices inicial e final são diferentes;
>   - **Caminho fechado ou circuito**: nenhum vértice (exceto o 1º e o último) aparece mais de uma vez.

## Grafos Eulerianos

**Problema do explorador:** um explorador deseja explorar todas as estradas entre um nº de cidades. É possível encontrar um trajeto fechado que passe por cada estrada apenas uma vez e volte à cidade inicial? (Ex.: Pontes de Konigsberg).

Em grafos **conexos**, se é possível encontrar um trajeto fechado que passe por **todas** as arestas uma única vez, dizemos que G é um **grafo euleriano**.

- Um **trajeto fechado** que utilize todas as arestas de um grafo, uma única vez, é chamado de **percurso euleriano fechado**.

### Teorema

Um grafo conexo, **não orientado** é euleriano se, e somente se, **todos** os seus vértices tiverem **grau par**.

> Bastante útil na produção de algoritmos de reconhecimento.

#### Lema 1 - Resultado auxiliar

Se todos os vértices de G possuem grau >= 2, então G contém um ciclo.

Se achar um ciclo que não passa por todas as arestas do grafo, podemos dividir esse ciclo do grafo, e  verificar se os componentes possuem um trajeto euleriano fechado, se possuirem, o grafo é euleriano. 

### Algoritmo de Hierholzer (1873)

Algoritmo para encontrar o caminho euleriano:

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/hierholzer.png" style="width:90%">

---

# Caminhos e Circuitos - Parte 2-2

19/08 :watch:

## Problema do carteiro chinês

Um carteiro deseja entregar cartas ao longo de todas as ruas de uma cidade, e retornar ao ponto inicial. Como ele pode planejar as rotas de forma a minimizar o caminho andado? 

> Consiste em encontrar um caminho mais curto ou circuito fechado que visite cada aresta de um grafo não-direcionado..

- Se o grafo for euleriano, basta percorrer o ciclo de Euler.
- Caso contrário, algumas arestas serão percorridas mais de uma vez. Será utilizado o conceito de arestas artificiais.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/carteiro_chines.png" style="width:100%">

> O exemplo acima é um grafo unicursal.

### Grafos semi-eulerianos ou unicursais

Um grafo é dito unicursal ou semi-euleriano se ele possui **pelo menos um Trajeto Euleriano aberto.**

> Se adicionarmos uma aresta conectando os vértices iniciais e finais do trajeto euleriano, o grafo passa a ser euleriano.

- Um grafo é unicursal se, e somente se, ele possuir **exatamente 2 vértices de grau ímpar**.

#### Teorema

Em um grafo conexo G com exatamente 2K vértices de grau ímpar, existem K subgrafos disjuntos de arestas, todos eles unicursais, de maneira que juntos eles contêm todas as arestas de G. 

Ex.: 2*3 = 6 vértices de grau ímpar = 3 subgrafos unicursais.

<img src="../../imgs/4_Periodo/Algoritmos_Grafos/unicrusal.png" style="width:40%">
