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

:building_construction:

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

:building_construction:

- Facilita na comunicação entre os interessados no projeto, no desenvolvimento;

- Destaca desições iniciais, com impacto profundo;

- ...

## ARQUITETURA EM CAMADAS

:building_construction:

É um tipo de.... um estilo de arquitetura?

## ARQUITETURA MVC

:building_construction:

## CONCEITOS

- **Desempenho (performance):** velocidade de execução dos processos/funções;

- **Proteção:** visa resguardar as partes mais importantes do sistemas;

- **Segurança:** oferece mecanismos de acesso seletivos e seguros;

- **Disponibilidade:** Tempo em que o sistema está acessível aos usuários;

- **Manutenibilidade:** Facilidade de alterar, de manter operacional;

- **Escalabilidade:** capacidade de auemntar a quantidade de usuáários e/ou sua distribuição;

- **Robustez:** capacidade do sistema funcionar mesmo em condições anormais;

- **Cafiabilidade:** gerar respostas confiáveis, como previsto;

- **Portabilidade:** Capacidade de ser transferido de um host para outro;

- **Interoperabilidade:** Capacidade de operar com diferentes formatos de dados;

- **Eficiência:** Capacidade de fazer o que foi determinado com o menor custo computacional;

- **Capilaridade:** Capacidade de cobertura, de penetração numa rede de computadores;

- **Granularidade:** Grão grosso é que o componente faz muita coisa, e grão fino (microserviços...) faz coisas específicas;

- **Resiliência:** Capacidade de recuperação, em caso de erro ou falhas.

:calendar:18/02

## NORMA ISO-9126

- **Funcionalidade:** Fala mais sobre os requisitos não funcionais, do que os funcionais;
  
  - Adequação: Presença de conjunto de funções e sua apropriação para as tarefas.
    
    - **Não fazer mais do que o usuário deseja.** por mais que supra a necessidade, tu ta abrindo mais possibilidades erro, mais horas de trabalho, maior cursto, etc. Isso tudo sem necessidade, pois os usuários podem nem usa. *Gastar 80% do tempo em 20% da oferta não vale a pena. - [Regra de Pareto]([Lei de Pareto: o que é o princípio, regra 80/20 - Significados](https://www.significados.com.br/lei-de-pareto/))*
  
  - Acurácia: Gera resultados corretos;
  
  - Interoperabilidade:  Capacidade de interagir com outros sistemas.
  
  - Conformidade:  Estar de acordo com normas, convenções e regulamentações. Compliance;
  
  - Segurança de acesso: Capacidade de evitar acesso não autorizado a programas e dados.

- **Confiabilidade** 
  
  - Maturidade: Frequência de falhas;
  
  - Tolerância a falhas: Manter nível de desempenho em caso de falha. Perdemos dados se uum serviço ficar fora? O sistema todo para se tivermos uma falha?
  
  - Recuperabilidade: Capacidade de restabelecer e restaurar dados após falha.

- **Usabilidade:** As três caracteristicas apontam para facilidade de uso.
  
  - Inteligibilidade: Facilidade de entender os conceitos utilizados. É intuitivo. Não preciso de um curso pra aprender;
  
  - Apreensibilidade: Facilidade de aprendizado;
  
  - Operacionalidade: Facilidade de operar e controlar a operação.

- **Eficiência**
  
  - Comportamento em relação ao tempo: Tempo de resposta de processamento;
  
  - Comportamento em relação a recursos: Qunatidade de recursos utilizados.

- **Manutenibilidade:** 
  
  - Analisabilidade: Facilidade de diagnóstigo;
  
  - Modificabilidade: Facilidade de modificação e remoção de defeitos;
  
  - Estabilidade: Ausência de riscos de efeitos inesperados;
  
  - Testabilidade: Facilidade de ser testado.

- **Portabilidade:** Posso pegar meu sistema e colocar/instalar em outros lugares. Ex.: Java tem alta portabilidade.
  
  - Adaptabilidade
  
  - Capacidade para ser instalado
  
  - Conformidade: Acordo com padrẽs ou convenções de portabilidade;
  
  - Capacidade para substituir.

## NORMA ISO-25010

Substitui a anterior.

Não atende a todos os aspectos cobertos pelos requisitos arquiteturais, pois podem ser aspectos muito específicos de cada caso.

:building_construction:

---

# SISTEMAS DISTRIBUIDOS

:calendar:25/02

> Estudar exercício de conceitos de SD!

Oposto de sistemas monoliticos.

- Monolitos
  
  - Basicamento toda a aplicação está centralizada.

> Mainframe: Núcleo central, grande estrutura.
> 
> Note: Vários terminais podem se ligar a um mainframe. Ou seja, várias máquinas só recebem e exibem os dados.

Sistemas distribuidos aumentam a complexidade, por poder se tratar de programação poliglota (podendo ser vantagem também!!), usa muito mais rede para se comunicar, uma infra maior, etc.

Tanenbaum: *"Coleção de computadores independentes que se apresenta ao usuário como um sistema único e consistente."*

![""](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/Aplicacoes_Distribuidas/2022-02-25-19-40-17-image.png)

<mark>Escalabilidade sem distribuição?</mark>

Basicamente, um sistema monolítico se caracteriza, principalmente, pelo grande acoplamento que ele possui, ou seja, ele é um grande bloco de código onde todas as funcionalidades estão. Ao contrário de uma aplicação distribuída que possui baixo acoplamento, mais integrações entre os sistemas, ou seja, uma granularidade maior.

Temos cenários mais adequados para usar cada tipo de sistema, como:

- Um sistema monolítico, por se tratar de um sistema fechado, ou seja, não possuir muitas interfaces de acesso… é mais seguro, logo podemos utilizá-lo no “core” de um sistema cujos processos são críticos. Ou em um cenário que seu acesso possa se restringir em uma rede local, deixando o sistema ainda mais seguro, como um sistema de controle de estoque, ou de uma barbearia, que não há a necessidade de acesso remoto e de um gasto financeiro maior com um sistema distribuído.

- Já em uma aplicação distribuída podemos utilizar em cenários que precisam de uma alta escalabilidade, ou que podem sofrer com mudanças constantes em suas regras de negócio ou na própria aplicação.

> Note: Um monolito é mais seguro por ter menos interfaces na rede, diminui o número de possibilidade de acesso, ou seja, quanto mais camada, mais possiblidades de acesso e mais vulnerável será.

:building_construction:

## MIDDLEWARE

Middlewares são camadas intermediárias que, valendo-se da abstração, provêm coesão e integração para os sistemas distribuídos. Essa camada, ou camadas, de abstração é que permite que a heterogeneidade característica de sistemas distribuídos não seja um obstáculo.

> Note: Lembrar do Framework Arch do Inter, abstrái toda a parte de autenticação, log, tracers, etc.

## ABERTURA

:building_construction:

ambiente fechado não permite acesso externo sem agregar camadas (SOAP, REST, GRAPHQL)

## SEGURANÇA

:building_construction:

## ESCALABILIDADE

:building_construction:

gargalos??

## MANIPULAÇÃO DE ERROS

:building_construction:

## TRANSPARÊNCIA

:building_construction:

## RECURSOS COMUNS EM SD

:building_construction:

---

# ESTILOS DE ARQUITETURIAS

:calendar: 04/03

:building_construction:

Uma arquitetura pode ser classificada segundo estilos de arquitetura.

<mark>Organizar o sistema</mark>

<mark>Grau de uniformidade</mark>

Um estilo é baseado **padrões** (Ex.: baseado em uml - poo, etc), **modelos** (Ex.: baseado em camadas, tipo do sistema, como se basear na arquitetura de um sistema de controle de estoque para criar outro) e **recursos** (Ex.: )

Cada estilo de arquitetura lida com diferentes atributos de qualidade. Logo, precisamos conciliar os atributos relevantes de uma arquitetura que queremos construir, com os atributos dos estilos para escolher o mais adequado àquele cenário.

Para elaborar uma arquitetura primeiro estudo as já existêntes, me baseio nela e faço as adequaões aos meus projetos.

- Uma arquitetura pode ser baseada em mais de um estilo;

- <mark>...</mark>



Exemplos:

- Cliente-Servidor

- Camadas

- Filtros e dutos (pipes and filters) (Lembrar do workflow)

- Repositório

- Orientado a eventos (publisher/subscriber)

- Objetos distribuídos

- Etc.



## ESTILOS SEGUNDO PRESSMAN



### ARQUITETURA CENTRADA EM DADOS

:building_construction:

### ARQUITETURA FLUXO DE DADOS

Ao contrário do modelo anterior, esse tem foco do processo, e não nos dados.

:building_construction:

### ARQUITETURA CHAMADA-RETORNO

:building_construction:

Existe um programa gerenciador.

### ARQUITETURA EM CAMADAS

:building_construction:





## ESTILOS SEGUNDO SOMMERVILLE



### DADOS COMPARTILHADOS (REPOSITÓRIO)

:building_construction:

- Vantagens:
  
  - asd

- Desvantagens:
  
  - asd

### CLIENTE / SERVIDOR

:building_construction:

### CAMADAS

:building_construction:

### MODELO DECOMPOSIÇÃO MODULAR

:building_construction:

### ORIENTADO A OBJETOS

:building_construction:

- Vantagens:
  
  - asd

- Desvantagens:
  
  - asd

### FLUXO DE DADOS

:building_construction:

### MODELOS DE CONTROLE

:building_construction:

### CONTROLE CENTRALIZADO

:building_construction:

### CHAMADA / RETORNO

:building_construction:

### MODELOS DIRIGIDOS POR EVENTOS

:building_construction:

### MODELO DE TRANSMISSÃO

:building_construction:

### BROADCASTING

:building_construction:

### CONTROLADO POR INTERRUPÇÕES

:building_construction: