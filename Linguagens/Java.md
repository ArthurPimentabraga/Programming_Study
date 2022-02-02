---
title: Java
author: Arthur P. Braga
---

## Java Compilation

O programa Java é compilado por uma forma intermediária denominada bytecode, que é interpretada pela JVM (Máquina Virtuai Java - já está junto com JDK). Por isso tal linguagem é tão independente de plataforma,  pois qualquer sistema que tiver uma JVM é capaz de rodar Java;

1. O compilador do Java (javac - tbm vêm no JDK) converte o código fonte (arquivo .java) em bytecodes  (arquivos .class);
2. A JVM armazena os bytecodes na memória RAM;
3. Enquanto os bytecodes são executados, os mesmos são verificados para certificar que não há violação de segurança Java. O Java certifica que os programas que chegam pela rede não vão danificar os arquivos ou sistema (como vírus worms);
4. A JVM executa os bytecodes no programa;

**Bytecodes ->** representam as tarefas a serem executadas na execução do programa;

---

## Commands and codes

```java
.substring(x,x) -> "Corta" um string de um caracter inicial(posicional) até outro.
.charAt(x) -> Retorna o caracter da string na posição escolhida dentro do parênteses;
.replace("x","x") -> Troca determinados caracteres de uma string por outros caracteres; 
.indexOf("x") -> Retorna a posição da 1ª aparição de x na String;
.lastindexOf("x") -> Retorna a posição da última aparição de x na String;
.startsWith("x") -> Retorna boolean, verifica se a String começa com x nesse caso;

Arrays.asList() -> Converte um array em uma lista;
.contains(x) -> Verifica se contém o x em uma lista, por exemplo;  
```

# Java Reflection

Java Reflection nada mais é que um conjunto de APIs da JVM que executam testes e alterações no código em tempo de execução.

As annotations geram o código usando a API Java Reflection, logo frameworks como SpringBoot que tem como padrão o desenvolvimento com anotações é comum o alto uso de memória e um tempo de boot mais demorado, uma vez que ta sendo executado todos esses testes e alterações (necessário analizar todos os beans em busca de anotações e então gerar metadados para essas anotações que eram armazenados em memória.).

O Micronaut, por exemplo, veio com a ideia de resolver esse problema, ele diminiu ao máximo o uso de reflection, mantendo só em casos específicos.

Que alterações podem ser essas?
