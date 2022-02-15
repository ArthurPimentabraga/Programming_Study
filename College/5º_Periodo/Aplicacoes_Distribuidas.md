---
title: Desenvolvimento de aplicações distribuidas (Puc-Minas - 5º Período)
author: Arthur Pimenta Braga
period: 1/2022
bibliography: Sistemas Distribuídos Princípios e Paradigmas - Tanenbaum
Microsserviços Prontos Para a Produção - Susan J. Fowler
Arquitetura Limpa - Robert C. Martin
Qualquer um do Martin Fowler
---

# INTRODUÇÃO

:calendar: 04/02

centralizado <> distribuído

Ou seja, um sistema distribuido em microserviços, camadas, por rede, IoT, mobile, etc. Um sistema que não está tudo concentrado em um único lugar. 

## EMENTA

- Fundamentos, tipos e modelos de Sistemas Distribuídos;

- Estratégias de comunicação em aplicações ditribuídas;

- Middlewares;

- Arquitetura e Linguagens de programação de aplicações Web;

- Arquitetura baseada em serviços;

- Ambientes de desenvolvimento e frameworks de back end.

---

# INTRODUÇÃO - ARQUITETURA DE SOFTWARE

## CONCEITOS

- Arquitetura de software envolve estabelecer precissas, definir requisitos, padrões, recursos, etc.

- "Ponte" entre modelo conceitual e físico.

> Topic: Arquitetura como "Design"

Arquitetura de software é a **estrutura de um sistema**, compreendida por:

- Componentes;
  
  - Pode ser considerado de várias formas: uma classe, um serviço, etc.

- Propriedades visíveis 
  
  - (Ex.: Operações que uma classe fornece);

- O relacionamento entre eles.

Um desenho arquitetural representa os componentes, seus relacionamentos, etc.

"Arquitetura é o conjunto de decisões significativas sobre a organização de um sistema de software."

> Ler também a atividade: ED1 - Arquiteto de sw!

> Note: Visões Arquiteturais (RUP)

:calendar: 11/02

**Stakeholders:** São as pessoas importantes, relevantes para a arquitetura do projeto, como: Gerentes, arquitetos, desenvolvedores, QAs, usuários, etc.

## DETALHAMENTO DA ARQUITETURA

<mark>Acabar aqui</mark>

- **Macroarquitetura:**  estilos arquiteturais (Ex.: microserviços....)

- **Microarquitetura:** ja é a comunicação entre eles.....

> Note: Tem que passar pelo macro antes do micro pra melhor aproveitamento.

### ESCOPOS DE ARQUITETURA

<mark>GUARDA CHUVA!!!!</mark>

Enterprise architecture decisions -> Ex.: Parceria com AWS.....

Domain Scope -> Ex.: Aplicação móveis - Aplicações Web

Aplication scope -> Decisão de 

Component scope -> vai usar serviço de mesageria nesse projeto?....

<mark><<<<<<<<<<< >>>>>>>>>>></mark>

- **Meta-Arquitecture:** Guias de arquitetura, arquiteturas de referências, servem como base para a definição arquitetural da empresa....

- **Architecture:** 

- **Architecture Guidelines and Policies:** Documentos arquiteturais que servem para orientar as pessoas.

Diagramas comportamentais e estruturais!!!

Arquitetura no processo!!

<mark><<<<<<<<<<< >>>>>>>>>>></mark>

## IMPORTÂNCIA DA ARQUITETURA

<mark>Acabar aqui</mark>

- Facilita na comunicação entre os interessados no projeto, no desenvolvimento;

- Destaca desições iniciais, com impacto profundo;

- ...

## ARQUITETURA EM CAMADAS

<mark>Acabar aqui</mark>

É um tipo de.... um estilo de arquitetura?

## ARQUITETURA MVC

<mark>Acabar aqui</mark>

## CONCEITOS

- **Desempenho (performance):** velocidade de execução dos processos/funções;

- **Proteção:** visa resguardar as partes mais importantes do sistemas;

- **Segurança:** oferece mecanismos de acesso seletivos e seguros;

- **Disponibilidade:** Tempo em que o sistema está acessível aos usuários;

- **Manutenibilidade:** Facilidade de alterar, de manter operacional;

- **Escalabilidade:** capacidade de auemntar a quantidade de usuáários e/ou sua distribuição;

- **Robustez:** capacidade do sistema funcionar mesmo em condições anormais;

- **Cafiabilidade:** gerar respostas confiáveis, como previsto.

- **Portabilidade:** Capacidade de ser transferido de um host para outro;

- **Interoperabilidade:** Capacidade de operar com diferentes formatos de dados;

- **Eficiência:** Capacidade de fazer o que foi determinado com o menor custo computacional;

- **Capilaridade:** Capacidade de cobertura, de penetração numa rede de computadores.

- Granularidade: Grão grosso é que o componente faz muita coisa, e grão fino (microserviços...) faz coisas específicas.

- Resiliência: Capacidade de recuperação, em caso de erro ou falhas.