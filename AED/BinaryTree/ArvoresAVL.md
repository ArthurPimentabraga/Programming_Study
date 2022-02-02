---
title: Árvores AVL
author: Guilherme Dantas Caldeira Fagundes
---

# Árvores AVL

## Conceitos Básicos

* No pior caso, o custo de comparação para se localizar um elemento em uma árvore AVL é de 1.44 x lg(n) = Θ(lg(n))

* Cada nó possui um fator de balanceamento que consiste na diferença entre o número de níveis de suas subárvores a direita e a esquerda

        fatorDeBalanceamento(i) = alturaDir(i) - alturaEsq(i), sendo i o nó que está sendo analisado no momento

* Cada nó conhece somente o seu fator de balanceamento

* Quando o fator de um nó se torna menor que -1 ou maior que 1 rotações devem ser feitas para que o balanceamento seja atingido, essa rotações são as descritas em [Balanceamento de Árvores Binárias](BalanceamentoArvoreBinaria.md).

As devidas rotações estão descritas na tabela abaixo

|   Fator do Nó  |  Fator do Filho à Direita    |   Fator do Filho à Esquerda   |   Tipo de Rotação   | 
|:-:|:-:|:-:|:--:|
|   2   |   1 ou 0   |            |  Simples à Esquerda       |
|   2   |   -1       |            |  Dupla Direita-Esquerda   |
|   -2  |            |  -1 ou 0   |  Simples à Direita        |
|   -2  |            |     1      |  Dupla Esquerda-Direita   |



