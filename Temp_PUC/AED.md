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

*Técnica de força bruta pra preencher um sudoku levaria 750.000.000 anos*

Para saber o custo de um algoritmo você executa um programa e mede o tempo.

**Passos:** Para que serve o algoritmo -> Qual a operação mais importante -> Quanto tempo se gasta?
