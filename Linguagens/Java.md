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
