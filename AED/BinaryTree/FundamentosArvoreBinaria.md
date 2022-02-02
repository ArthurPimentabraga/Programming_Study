---
title: Fundamentos De Árvore Binárias
author: Guilherme Dantas Caldeira Fagundes
---

# Fundamentos de Árvore Binárias

## Conceitos Básicos

* Custo de inserção, remoção e pesquisa em árvores pode ser dado como Θ(lg(n)) comparações
* Formada por um conjunto finito de nós conectados por arestas
* Possui um ponteiro que aponta para a raiz da árvore
* Um nó com filhos é chamado de nó interno, um nó sem filhos é chamado de folha

## Árvore Binárias
* Cada nó possui no máximo 2 filhos

### Árvore Binária de Pesquisa

* Árvore Binária em que cada nó é **maior** que todos seus vizinhos a esquerda e **menor** que todos seu vizinhos a esquerda. Ou seja, os nós descendentes a direita são menores que ele e os
nós descendentes a direita são maiores que ele.

### Árvore Binária Completa
* Cada nó é uma folha ou possui exatamente dois filhos
* Todos os nós folhas possuem uma altura h
* O número de nós internos é dado por 2<sup>h</sup> - 1
* O número de nós folhas é de 2<sup>h</sup>
* O número total de nós é dado por 2<sup>(h + 1)</sup> - 1

## Árvore Balanceada

* Árvore em que para **todos** os nós, a diferença entre a altura de suas árvores da esquerda e da direita sempre será 0, 1 ou -1.

## Implementações em Código de um Nó

```java
class No{
    int elemento; // O elemento pode ser um objeto

    // Ambos nós funcionam como ponteiros para os filhos de this 
    No esq;
    No dir;

    No(int elemento){
        this(elemento, null, null);
    }

    No(int elemento, No esq, No dir){
        this.elemento = elemento;
        this.esq = esq;
        this.dir = dir;
    }
}
```

## Funcionamento dos Métodos em uma Árvora Binária de Pesquisa

### Inserção
1. Se a raiz estiver vazia, o elemento inserido se torna a raiz
2. Se o novo elemento for menor que a raiz, é feita uma recursão para que o elemento seja inserido na subárvore da esquerda
3. Se o novo elemento for maior que a raiz, é feita uma recursão para que o elemento seja inserido na subárovre da direita 

#### Análise de Complexidade da Inserção
* Melhor caso: Θ(1) comparações, acontece ao inserir um elemento na raiz
* Pior caso: Θ(n) comparações, acontece quando a inserção dos elementos é feita em ordem crescente ou decrescente
* Caso médio: Θ(lg(n)) comparações, acontece quando a inserção é feita em uma folha de uma árvore balanceada

### Pesquisa
1. Se raiz estiver vazia, retorna um valor negativo
2. Se o elemento procurado for igual ao da raiz, retorna uma pesquisa positiva
3. Se o novo elemento for menor que a raiz, é feita uma recursão para que o elemento seja procurado na subárvore da esquerda
4. Se o novo elemento for maior que a raiz, é feita uma recursão para que o elemento seja procurado na subárovre da direita 

#### Análise de Complexidade da Pesquisa
* Melhor caso: Θ(1) comparações, acontece quando a raiz está vazia ou o elemento pesquisado está na raiz
* Pior caso: Θ(n) comparações, acontece quando a inserção dos elementos é feita em ordem crescente ou decrescente e o elemento desejado está na folha da árvore, operando basicamente como uma estrutura linear
* Caso médio: Θ(lg(n)) comparações, acontece quando a árvore está balanceada e procuramos um elemento localizado em uma folha

### Caminhamento

* Baseia-se em percorrer todos os nós da árvore
* A complexidade é de Θ(n) pois todos os nós devem ser visitados

Existem alguns tipos de caminhamentos:
* Caminhamento Central (em ordem): Percorrer os nós, exibindo-os em ordem crescente
* Caminhamento Pós-Fixado (pós-ordem): Executa o caminhamento sobre a subárvore a direita de um nó i recursivamente
* Caminhamento Pré-Fixado (pré-ordem):Executa o caminhamento sobre a subárvore a esquerda de um nó i recursivamente