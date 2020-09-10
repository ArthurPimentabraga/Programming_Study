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

- **Ordem de complexidade - O(n)**. Uma função vai ser da ordem de complexidade da outra com ela tem o mesmo comportamento que essa outra. Essa ordem de complexidade é aproximadamente o limite em que tal algoritmo é "viável".

**Classes de complexidade**

- Complexidade **fixa ou constante** (melhor caso possível, porém limitado): Uma complexidade constante executa um nº fixo de vezes independente do tamanho de n (da quant de dados). Ex: Um array ordenado que pega o maior elemento. Ex2: Fazer uma troca de dois nº de posição em um array;

- Complexidade **logarítmica**: Resolve problemas transformando-os em problemas menores. Se o algoritmo resolve diviindo o problema a cada passo. Ex: Busca binária;

- Complexidade **Linear**: Um trabalho é realizado sobre cada elemento de entrada. Ex: Procurar um elemento em um array desordenado;

- Algoritmos **n*log n**: Quebram o problema em partes menores, mas resolve cada um deles independentes e depois agrupam as soluções (dividir para conquistar);

- Algoritmos **quadráticos**: O(n²) itens processados aos pares. Para problemas relativamente pequenos.  Ex: Um loop dentro do outro.

- Algoritmos **cúbicos**: O(n³) Sempre que n dobra, o tempo é multiplicado por 8. Ex: 3 loops, um dentro do outro. Multiplicação de matrizes;

- Algoritmos **exponenciais**: O(2^n) Não são úteis sob o ponto de vista prático. Sempre que n dobra, o tempo é elevado ao quadrado. Ex: Força bruta;

- Complexidade **Fatorial**: O(n!) Comportamento muito pior do que O(2^n). Ou seja, em vez de 2x2x2x2... vai ser 2x3x4x6.... Ex: Para o nº 40 em um algoritmo desse, executado no PC mais poderoso do mundo demoraria SÉCULOS; 
