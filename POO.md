---
title: Programação Orientada à Objetos
author: Arthur P. Braga
description: Mesclado com anotações da matéria que tive na PUC.
---

## General

- **Classe and Objeto ->** Classe é uma estrutura de um conjunto de entidades com características similares, é o "esquema/representação" de uma "entidade genéria". E objeto é a instância de uma classe, é um "exemplar" daquela classe. Ex: Classe: User || Objeto: João, Carlos, Camila...
- **Classe Abstrata ->** Nunca será instânciada. É uma classe criada para ser herdada. Ex: Uma classe abstrata "animal" é herdada pelas classes "cachorro", "gato"...
- **Interface ->** É um conjunto de métodos públicos sem implementação. Ou seja, é criada para seus métodos serem herdados, porém todo código dos mesmos será feito nas classes que herdarem dessa interface, tornando os métodos exclusivos e diferentes para cada classe. Ex: Uma interface com os métodos "ligar" e "acelerar", e ambas as classes "carro" e "moto" herdam dessa interface, porém o código do "ligar" e ''acelerar" será feito nas classes "carro" e "moto" separadamente;  
- **Single responsibility ->** Um conceito de POO. Seu sistema deve dividir cada camada, por exemplo, com cada uma contendo seu objetivo único. Ou seja, nenhuma camada ou parte do sistema, pode fazer outra coisa além do que foi destinada a fazer;
- **Getter, Setter and Contructor ->** 

---

## Pilares

- **Abstração ->** Abstrair um objeto do mundo real no nosso sistema, trazendo todas as suas características e ações para dentro do nosso sistema;

- **Encapsulamento ->** É uma técnica que "esconde" os objetos, deixa eles privados e sem acesso direto à eles. Geralmente usando getters e setters para retornar e setar os valores;

- **Herança ->** Classes podem herdar outras classes, fazendo com que elas recebam todos os atributos e métodos da classe "pai" (caso os mesmos tenham visibilidade public ou protected);

- **Polimorfismo ->** Consiste na alteração (quando necessário) de um funcionamento interno de um método herdado de um objeto pai;

---

## Vantagens

- Modularidade - Consequentemente mais seguro, pois divide o sistema e permite modificar um lugar sem alterar o outro;
- Manutenção facilitada;
- Extensível;
- Reutilizável.
