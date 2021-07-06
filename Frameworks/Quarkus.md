---
title: Quarkus - Framework Java
author: Arthur P. Braga
---

## What is

Quarkus é um framework Java nativo em Kubernetes, adaptado para GraalVM, e desenvolvido para JVMs e compilação nativa. Projeto OpenSource mantido pela Red Hat. Ele otimiza essa linguagem especificamente para containers, fazendo com que essa tecnologia seja uma plataforma eficaz para ambientes **serverless**, de **nuvem** e **Kubernetes**. 

Por causa da compatibilidade avançada com o GraalVM é possível desenvolver uma aplicação com compilação nativa, ou seja, ao invés da compilação padrão do java onde o código é compilado em formato bytecode, armazenado na memória RAM e transformado em código binário, o GraalVM  compila o código direto para binário. Nesse processo, a GraalVM aplica uma série de otimizações bem agressiva. Somando essas otimizações, a retirada das classes inúteis, com a compilação do código para nativo, o resultado final é um arquivo executável pequeno, rápido de executar e com baixo consumo de memória.

### Secondary meanings

*Kubernetes: é uma plataforma open source que automatiza as operações dos containers Linux. Essa plataforma elimina grande parte dos processos manuais necessários para implantar e escalar as aplicações em containers.*

*GraalVM: Projeto criado pela Oracle para melhorar a performance das aplicações e diminuir o consumo de memória atendendo principalmente a necessidade de aplicações no ambiente de nuvem, onde a principal tarefa é criar uma nova Máquina Virtual para substituir a JVM do Java.*

---

## Benefits

- Baixo uso de memória e alta velocidade de boot. Possível pela compatibilidade avançada com o GraalVM.
- Codificação dinâmica, SEM REDEPLOY. Como o hot reload em Flutter, podemos simplesmente salvar o projeto, e já é possível verificar toda alteração feita imediatamente.
- Geração executável nativa e fácil.
- ESTUDAR ESSA PARTE - Programação imperativa e reativa unificada com um barramento de eventos gerenciado e integrado. Vert.x.................

---

## References

- Site oficial Quarkus - https://quarkus.io/
- Red Hat (Quarkus) - https://www.redhat.com/pt-br/topics/cloud-native-apps/what-is-quarkus#:~:text=Quarkus%20%C3%A9%20um%20framework%20Java,serverless%2C%20de%20nuvem%20e%20Kubernetes.
- GraalVM - https://www.zup.com.br/blog/graalvm
- Compilação nativa - https://dev.to/lucasscharf/uma-breve-explicacao-sobre-o-modo-nativo-do-quarkus-1kn7
- Red Hat (Kubernetes) - https://www.redhat.com/pt-br/topics/containers/what-is-kubernetes

- https://quarkus.io/vision/continuum →Paradigmas

- https://www.youtube.com/watch?v=spWnqkbFgH4 → Quarkus explication