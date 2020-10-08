---
title: Algoritmos e Estrutura de Dados (Puc-Minas - 2º Período)
author: Arthur P. Braga
---

### Notes

**1ª e 2ª Aula ->** Como vai ser a aula e formação de grupos de trabalho;

**3ª Aula ->** Tipo abstrato de dados (TAD - mesma coisa de classe abstrata);

**4ª Aula ->** Continuação da explicação de TAD || Java Extension Pack (VSCode)

---

**5ª e 6ª Aula ->** Recursividade

- Descubra a **repetição**, depois a **regra de formação** e depois o **ponto de parada**.

Exemplo de uma multiplicação usando recursividade:

```java
public static void main(String[] args) {
  System.out.println("A multi = "+mult(2, 3));
}

public static int mult(int n1, int n2){
  if (n1 == 0) return 0;
  else return n2+mult((n1-1), n2);
}
```

---

**7ª Aula ->** Busca binária (pesquisa sequencial) e debate te atividades

---

**8ª Aula ->** Introdução a análise de complexidade de algoritmos

- Regras precisas;

- Cobrir todos os pontos de parada;

- Consumir o menor nº de recurso no menor tempo possível;

*Técnica de força bruta pra preencher um sudoku poderia levar 750.000.000 anos*

Para saber o custo de um algoritmo você pode executar um programa e medir o tempo.

**Passos:** Para que serve o algoritmo -> Qual a operação mais importante -> Quanto tempo se gasta? (equação) IMPORTANTE!!!!!

Existem três cenários: 

- Pior caso -> f(n) = n

- Melhor caso -> f(n) = 1

- Caso Médio -> f(n) = (n+1)/2.

Todos se relacionando com a quantidade de trabalho que foi necessário para alcançar o objetivo; 

---

**9ª Aula ->** Exemplos de análise de complexidade de algoritmos

<img title="" src="file:///home/arthurbraga/Documentos/Programming_Study/imgs/Analise_Algoritmo.png" alt="">

f(n) = 2*(n-1) ou f(n) = 2n - 2 

---

**10ª Aula ->** Continuação análise de algoritmos

- **Comportamento assintótico**:  É o comportamento das funções de custo para valores grandes de n. Assintota.

- **Ordem de complexidade - O(n)**. Uma função vai ser da ordem de complexidade da outra quando ela tem o mesmo comportamento que essa outra. Essa ordem de complexidade é aproximadamente o limite em que tal algoritmo é "viável".

**Classes de complexidade**

- Complexidade **fixa ou constante** (melhor caso possível, porém limitado): Uma complexidade constante executa um nº fixo de vezes independente do tamanho de n (da quant de dados). Ex: Um array ordenado que pega o maior elemento. Ex2: Fazer uma troca de dois nº de posição em um array;

- Complexidade **logarítmica**: Resolve problemas transformando-os em problemas menores. Se o algoritmo resolve divindo o problema a cada passo. Ex: Busca binária;

- Complexidade **Linear**: Um trabalho é realizado sobre cada elemento de entrada. Ex: Procurar um elemento em um array desordenado;

- Algoritmos **n*log n**: Quebram o problema em partes menores, mas resolve cada um deles independentes e depois agrupam as soluções (dividir para conquistar);

- Algoritmos **quadráticos**: O(n²) itens processados aos pares. Para problemas relativamente pequenos.  Ex: Um loop dentro do outro.

- Algoritmos **cúbicos**: O(n³) Sempre que n dobra, o tempo é multiplicado por 8. Ex: 3 loops, um dentro do outro. Multiplicação de matrizes;

- Algoritmos **exponenciais**: O(2^n) Não são úteis sob o ponto de vista prático. Sempre que n dobra, o tempo é elevado ao quadrado. Ex: Força bruta;

- Complexidade **Fatorial**: O(n!) Comportamento muito pior do que O(2^n). Ou seja, em vez de 2x2x2x2... vai ser 2x3x4x6.... Ex: Para o nº 40 em um algoritmo desse, executado no PC mais poderoso do mundo demoraria SÉCULOS; 

---

**11ª Aula ->** Estrutura de dados

**Memória principal ->** "imenso array" de bytes.

Declaração de variável é uma abstração dos endereços de memória.

Cada variável tem seu nome, endereço e valor;

**Ponteiros ->** É uma variável que armazena um endereço de memória. Usado com Strings, por exemplo. Ou seja, como o tamanho da String depende, e pode variar muito, ele só faz uma referência para a área da memória que caiba a String.

*Tipos básicos: valores copiados - Objetos: referência*

**Alocação dinâmica de memória:** Ele reserva um espaço para um ponteiro, para futuramente poder fazer uma referência. 

---

**12ª Aula ->** Estruturas de dados -> **Filas**

*Dados "ordenados" por chegada - first in first out (FIFO)*

Exemplos em sistemas:

- Atendimento Bancário;

- Pedidos de reservas na biblioteca;

- Processamento de alteração de matrículas;

- Venda de ingressos.

**Fila estática:** Tem um tamanho fixo, podendo ou não estar totalmente ocupado. Um vetor pode ser usado para representar uma fila simples, mas não é uma fila, pois não tem regra (qualquer um pode sair a qualquer hora....).

Para isso precisa de um vetor e duas variáveis (capacidade do vetor e quantidade contida ele).

*Os valores sempre vão entrar atrás da posição do ultimo valor (que será a variável qtd).*

Valor de escape: valor que nunca terá seu lugar na fila.

---

**13ª Aula ->** Continuação de Filas

**Filas Dinâmicas (ou encadeadas):** Seus elementos são inseridos e retirados ao longo da execução do programa - dinamicamente. Não tem uma previsão da memória total necessária e nem previsão da quatidade de alterações necessárias quando se retira um valor.

- O elemento da fila inclui uma referência para o próximo elemento (ponteiro). Logo pode-se criar um novo elemento e apontar para outro.

- *Potencialmente infinito*

---

**14ª Aula ->** Listas encadeadas

*Interligação de elementos - Pode ter um ordenamento ou não.*

- Não há uma regra de inserção e retirada;

- Difícil de prever a demanda de memória total necessária.

Ex: Lista de trabalhos - Controle de processos em um SO...

*A estrutura da fila e da lista é a mesma, o que muda é a regra!*

**Métodos de lista:** Inserir - Deletar - Localizar - Concatenar listas

- **Localizar:** 
  
  1. A partir do início, avançar i posições na lista.
  
  2. Localizar pelo valor.

- **Retirar da posição i:** Primeiro a gente precisa localizar. 

**Listas duplamente encadeadas:**

*Passa a ter duas referencias por elemento. - Dois apontadores, um para o próximo elemente, e outro para o anterior.*

---

**15ª Aula ->** Pilhas

*Estrutura empilhada, ou seja, coloca e retira dados somente por cima.*

*LIFO (last in, first out)*

**Usos**:

- Analogia clássica: pilha de pratos (Não faz diferença se você pegar o 1º dado, ou o último, ou qualquer outro);

- Chamadas de funções;

- Crtl+Z;

- Debug;

- Inversões (pois o ultimo q entra é o primeiro que sai).

*Pode criar um contador para limitar o uso de memória.*

**Notação polonesa reversa (pós-fixa):** modo como escreve as operações para o computador interpretar corretamente (a operação vem depois dos números).

Para usar a notação polonesa precisa de duas pilhas, uma para criar a equação polonesa e outra para resolver.

---

**16ª Aula ->** Árvores

Todas as estruturas anteriores eram *lineares* (seguir em linha reta vai passar por todos os dados) - As arvores são estruturas não-lineares, existem **caminhos** à se seguir, **com hierarquia**.

Exemplos: Estrutura de diretório do Unix S2; Git S2

*nodos (nós) ou vértices = elementos de uma árvore*

**Grau de um nodo:** Quantidade de descendentes diretos que ele tem. Elementos de grau 0 = folha;

**Nível de um nodo:** Distância do nodo até a raiz.

**Altura de um nodo:** Distância do nodo a folha mais distânte (pior caso de complexidade).

**Subárvore:** Conjunto de elementos com uma raiz comum

É uma estrutura recursiva, pois uma arvore é uma raiz e suas subárvores, e uma subárvore é uma árvore.

**Árvore binária de busca:** Cada nodo só tem até dois filhos e os valores à esquerda são sempre menores que os valores à direita.
