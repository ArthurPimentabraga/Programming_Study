---
title: Árvores 2-3-4
author: Guilherme Dantas Caldeira Fagundes
---

# Árvores 2-3-4

## Conceitos Básicos

* Árvore de pesquisa cujos nóes são de três tipos
    * 2-nó
    * 3-nó
    * 4-nó

* A altura de uma árvore 2-3-4 contendo *n* itens é Θ(lg(n))

* Também recebe o nome de B-Tree

### Pesquisa em Árvore 2-3-4

Dado um nó com 3 elementos, sendo eles x1, x2 e x3 em ordem crescente respectivamente, tem-se:

1. Verifica se o elemento está na raiz, se estiver retorna uma resposta positiva
2. Se o elemento o pesquisado for menor que x1, a pesquisa é feita na árvore da esquerda
3. Se o elemento for menor que x2 e não foi encontrado no passo **2**, a pesquisa é feita na árvore do meio à esquerda
4. Se o elemento for menor que x3 e não foi encontrado no passo **3**, a pesquisa é feita na árvore do meio à direita
5. Caso o elemento não tenha sido encontrado nos passo anteriores, a pesquisa é feita na árvore a direita

#### Complexidade da Pesquisa em Árvore 2-3-4
* Melhor caso: Θ(1)
* Pior/Caso Médio: Θ(lg(n))

### Inserção

**Vale ressaltar que os passos de inserção a seguir considera que as inserções serão feitas somente nas folhas por quesito de simplificação!**

* Se a folha tiver 1 ou 2 elementos, a inserção é feita nela
* Caso contrário, cria-se um novo nó e a reorganiza

A reorganização da árvore 2-3-4 é um ponto importante no processo de inserção. Ela pode ser feita de duas maneiras:

* Inserção com Fragmentação na Ascensão
    * Pode causar um efeito cascata de fragmentações
    * Caso o caminhdo da inserção seja formado inteiramente por 4-nós, a fragmentação irá ocorrer em todo o caminho

* Inserção com Fragmentação na Descida
    * Implementa-se a fragmentação ao percorrer o caminho da inserção, impedindo a existência de dois 4-nós seguidos, por isso, é dita como preventiva
    * Pode gerar fragmentações inúteis

