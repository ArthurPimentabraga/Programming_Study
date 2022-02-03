---
title: CountingSort
author: Guilherme Dantas Caldeira Fagundes
---

# CountingSort

## Funcionamento

Parte da quantidade de vezes que um valor ocorre. Possui
basicamente 3 vetores:

* Array de Entrada
* Array de Contagem -> Mapeia a quantidade que cada elemento aparece no vetor
* Array de Saída

**É perceptível a maior quantidade de memória que esse algoritmo ocupa já que ele utiliza de 3 vetores para executar a ordenação.**

**É mais utilizado para manipulação de valores inteiros ou registros tratados.**

**É um algoritmo estável.**

O algoritmo avalia quantas vezes um valor apareceu no valor de entrada e insere no array de contagem, as somas feitas e depois refaz a contagem chamada _contagem acumulativa_.

```java
    [2,5,3,0,2,3,0,3] -> Array de Entrada

    [2,0,2,3,0,1] -> Array de Contagem

    [2,2,4,7,7,8] -> Executa a Contagem Acumulada

    [0,0,2,2,3,3,3,5] -> Array de Saída
```

## Implementação

```java
   int[] count = new int[getMaior() + 1];
   int ordenado = new int[n];

   for(int i = 0; i < count.length; count[i] = 0, i++);

   for(int i = 0; i < n; count[array[i]++, i++);

   for(int i = ; i < count.length; count[i] += count[i - 1], i++);
```

## Análise das Operações

* Para inicializar todas as posições do array de contagem com 0: Θ(n)
* Para cada elemento do array de entrada, incrementar no array de contagem: Θ(n)
* Fazer com que o array de contagem seja acumulativo: Θ(n)
* Preencher o array de saída: Θ(n)

Tais operações totalizam o custo médio do algoritmo como Θ(n).