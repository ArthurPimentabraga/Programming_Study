---
title: ShellSort
author: Guilherme Dantas Caldeira Fagundes
---

# ShellSort

## Funcionamento

* Divide o array em h partes inicialmente.
* Executa o inserção nos respectivos grupos h.
* Divide o array em partes h / n.
* Executa o inserção nos respectivos grupos h /n.
* Repete o processo até ter grupos de 1.
* Executa o inserção normalmente.

## Implementação

 ```java
   void shellsort(){
       int h = 1;
       do{
           h = (h * 3) + 1;
       }while(h < n); // Sendo n o número de elementos

       do{
           h /= 3;
           for(int group = 0; group < h; group++){
               insertionByGroup(group, h);
           }
       }
   }

   void insertionByGroup(int group, int h){
       for(int i = (h + group); i < n; i+=h){
           int tmp = array[i];
           int j = i - h;

           while((j >= 0) && (array[j] > tmp)){
               array[j + h] = array[j];
               j-=h;
           }

           array[j+h] = tmp;
       }
   }

   void insercao(){
       for(int i = 1; i < n; i += 1){
           for(int i = 1; i < n; i += 1){
               int tmp = array[i];
               int j = i - 1;

               while((j >=0 && (array[j] > tmp)){
                   array[j + 1] = array[j];
                   j-= 1;
               }

               array[j + 1] = tmp;
           }
       }
   }
```

## Análise do Número de Comparações

* A análise de complexidade depende da razão de incrementos (h). O h pode ser definido pelo desenvolvedor mas possui linhas teóricas mais consistentes que tentam encontrar a sequência mais otimizada.

* A sequência de Knuth possui duas conjecturas
    * Conjectura 1: C(n) = Θ(n^1.25)
    * Conjectura 2: C(n) = Θ(n(lnn)²)
* Vantagens:
    * Bom para sequência de tamanhos moderados
    * Implementação simples
* Desvantagens:
    * Seu tempo de execução é sensível ao arquivo original
    * Não estável



