---
title: Balanceamento de Árvores Binárias
author: Guilherme Dantas Caldeira Fagundes
---

# Balanceamento de Árvores Binárias

## Conceitos Iniciais
* Árvores balanceadas aumentam a eficiência das pesquisas, inserções e remoções
* Todas árvores inicialmente são balanceadas e elas podem ficar desbalanceadas após operações de remoção e inserção
* O balanceamento é feito através da rotação de nós

**É importante que o balanceamento seja feito logo depois que um nó seja inserido ou removido, aplicar balanceamento em uma árvore após finalizar todas as operações desejadas é muito mais custoso do que ao realizar imediatamente após cada operação.**

## Tipos de Rotação

### Rotação Simples à Esquerda

É feita em subárvores em que o pai e o filho estão desbalanceados para a direita. Ou seja, o filho é maior que o pai e o pai é maior que o avô. Ao executar essa rotação, tanto o filho quanto o avô se tornam filhos do pai.

Vale ressaltar que nessa rotação o avô fica a **esquerda** do pai.

### Rotação Simples à Direita

É feita em subárvores em que o pai e o filho estão desbalanceados para a esquerda. Ou seja, o filho é menor que o pai e o pai é menor que o avô. Ao executar essa rotação, tanto o filho quanto o avô se tornam filhos do pai.

Vale ressaltar que nessa rotação o avô fica a **direita** do pai.

### Rotação Dupla Direita-Esquerda

É feita em subárvores em que o pai e o filho estão desbalanceados e formam uma formação parecida com um >. Ou seja, o filho é menor que o pai e o pai é maior que o avô. Ao executar essa rotação, tanto o avô quanto o pai se tornam filhos do filho.

Vale ressaltar que nessa rotação o avô fica a **esquerda** do filho e o pai fica a **direita** do filho. 

### Rotação Dupla Esquerda-Direita

É feita em subárvores em que o pai e o filho estão desbalanceados e formam uma formação parecida com um <. Ou seja, o filho é maior que o pai e o pai é menor que o avô. Ao executar essa rotação, tanto o avô quanto o pai se tornam filhos do filho.

Vale ressaltar que nessa rotação o avô fica a **direita** do filho e o pai fica a **esquerda** do filho. 