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

- Arquitetura de software envolve estabelecer precisas, definir requisitos, padrões, recursos, etc.

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

> Ler também a atividade: [ED1 - Arquiteto de sw!]([ED1 - Arquiteto de sw - Documentos Google](https://docs.google.com/document/d/1dNWyxJU68HNVZOogi6le2ELGNj_uMYcPmb3fgvw3AWs/edit?usp=sharing))

> Note: Visões Arquiteturais (RUP)

:calendar: 11/02

**Stakeholders:** São as pessoas importantes, relevantes para a arquitetura do projeto, como: Gerentes, arquitetos, desenvolvedores, QAs, usuários, etc.

## DETALHAMENTO DA ARQUITETURA

- **Macroarquitetura:**  Define a arquitetura em aspectos mais gerais, com o estilo arquitetural que seguirá (Ex.: Centrada a dados, em camadas, etc. Acredito que microserviços também pode ser considerado, por ser em camadas, etc).
  
  - Feita no início do projeto;

- **Microarquitetura:** É um refinamento da macro, já descreve a comunicação entre os componentes, seu nível de granularidade, etc. Sendo possível o desenvolvimento com ela.
  
  - Vamos produzir ela quando tivermos os requisitos em mão, podendo modificar ao longo do desenvolvimento, etc.

> Note: Tem que passar pelo macro antes do micro pra melhor aproveitamento.

### ESCOPOS DE ARQUITETURA

Para conseguirmos seguir corretamente, e sem muitos problemas, o projeto arquitetural nas fases de implementação é importante definirmos os escopos:

![""](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/Aplicacoes_Distribuidas/2022-03-16-18-35-31-image.png)

- **Enterprise architecture decisions** (Arquitetura corporativa);
  
  - Decisões técnicas que envolvem toda a empresa (ACHO);
  
  - Ex.: Parceria com AWS, etc.

- **Domain Scope** (Arquitetura de domínio); 
  
  - Ex.: Aplicação móvel - Aplicação Web, etc.

- **Aplication scope** (Arquitetura de aplicação); 
  
  - Decisão de<mark>.....</mark> 

- **Component scope** (Arquitetura de componente);
  
  - Decisões limitadas aos componentes em específico, como: vai usar serviço de mesageria nesse projeto? Como será a comunição entre os microsserviços?

### NÍVEIS DE DECISÃO

:building_construction:

- **Meta-Arquitecture:** Guias de arquitetura, arquiteturas de referências, servem como base para a definição arquitetural da empresa....

- **Architecture:** 

- **Architecture Guidelines and Policies:** Documentos arquiteturais que servem para orientar as pessoas.

Diagramas comportamentais e estruturais!!!

Arquitetura no processo!!

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

> Atividade relacionada: [Conceitos de SD!]([Exercicio - conceitos SD - Documentos Google](https://docs.google.com/document/d/1YRiFEcX1--wWD1fWuhEE_Ak3IcaQBjEyg7QqacitrX8/edit?usp=sharing))

Oposto de sistemas monoliticos.

- Monolitos: Basicamento toda a aplicação está centralizada.

> Mainframe: Núcleo central, grande estrutura.
> 
> Note: Vários terminais podem se ligar a um mainframe. Ou seja, várias máquinas, sem poder de processamento, só recebem e exibem os dados.

Sistemas distribuidos aumentam a complexidade, por poder se tratar de programação poliglota (podendo ser vantagem também!!), usa muito mais rede para se comunicar, uma infra maior, etc.

Definição por Tanenbaum: *"Coleção de computadores independentes que se apresenta ao usuário como um sistema único e consistente."*

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

Rabbit MQ é um exemplo de middleware de mensageria. Podemos ter camada de microserviço de middleware... tudo que prover uma interface que facilita algum processo, e faz a ligação de uma camada a outra, é considerado um middleware.

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

> Atividade relacionada: [Estilos de arquitetura de SW]([Ex. estilos de arquitetura de sw - Documentos Google](https://docs.google.com/document/d/1u8_gZwa95bwAlIOUkzXJpjFk2_zo3QZJCsMEkk7wq6c/edit?usp=sharing))

:building_construction:

Analogia com design pattern... forma de resolver um problema, chegar a um objetivo.

Uma arquitetura pode ser classificada segundo estilos de arquitetura.

Taxonomia.

<mark>Organizar o sistema</mark>

<mark>Grau de uniformidade</mark>

*Um estilo é baseado **padrões** (Ex.: baseado em uml - poo, etc), **modelos** (Ex.: baseado em camadas, tipo do sistema, como se basear na arquitetura de um sistema de controle de estoque para criar outro) e **recursos** (Ex.: )*

*Cada estilo de arquitetura lida com diferentes atributos de qualidade. Logo, precisamos conciliar os atributos relevantes de uma arquitetura que queremos construir, com os atributos dos estilos para escolher o mais adequado àquele cenário.*

Para elaborar uma arquitetura primeiro estudo as já existêntes, me baseio nela e faço as adequações aos meus projetos.

- Uma arquitetura pode ser baseada em mais de um estilo;

Exemplos:

- Cliente-Servidor

- Camadas

- Filtros e dutos (pipes and filters) (Lembrar do workflow)

- Repositório

- Orientado a eventos (publisher/subscriber)

- Objetos distribuídos

- Etc.

## ESTILOS SEGUNDO PRESSMAN

• Centrado em dados (Repositório) 
• Fluxo de dados. 
• Chamada-retorno. 
• Orientada a objetos. 
• Camadas.

### ARQUITETURA CENTRADA EM DADOS

:building_construction:

![](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/2022-03-17-20-53-31-image.png)

### ARQUITETURA FLUXO DE DADOS

Ao contrário do modelo anterior, esse tem foco do processo, e não nos dados.

:building_construction:

![](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/2022-03-17-20-54-48-image.png)

### ARQUITETURA CHAMADA-RETORNO

:building_construction:

Existe um programa gerenciador.

Estrutura de programa relativamente fácil de modificar e ampliar,

![](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/2022-03-17-20-55-08-image.png)

### ARQUITETURA EM CAMADAS

:building_construction:

![](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/2022-03-17-21-01-21-image.png)

## ESTILOS SEGUNDO SOMMERVILLE

• Dados compartilhados. 
• Serviços e servidores compartilhados. 
• Máquina abstrata ou camadas

### DADOS COMPARTILHADOS (REPOSITÓRIO)

:building_construction:

Quando grandes quantidades de dados....

- Vantagens:
  
  - asd

- Desvantagens:
  
  - asd

### CLIENTE / SERVIDOR

:building_construction:

![](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/2022-03-17-21-21-21-image.png)

### CAMADAS

:building_construction:

Mesma coisa...

### MODELO DECOMPOSIÇÃO MODULAR

:building_construction:

- Modelo orientado a objetos;

- Modelo de fluxo de dados.

#### ORIENTADO A OBJETOS

:building_construction:

Decomposto em um conjunto de objetos que se comunicam (POO mesmo).

#### FLUXO DE DADOS

:building_construction:

Modelo pipeline, é decomposto em módulos funcionais que transformam entradas de dados em saídas.

Mesma coisa do Pressman.

Não é muito adequado para sistemas iterativos, é mais para sistemas de transformações sequênciais, de processamento de dados.

- Vantagens:
  
  - Apoia o reuso de transformações;
  
  - É intuitiva, pois pessoas pensam no sentido de entrada e saída;
  
  - Escalabilidade facilitada, ou seja, adição de novas transformações é direta;
  
  - Fácil de ser implementada tanto quanto um sistema concorrente ou sequêncial;

- Desvantagem:
  
  - Formato comum/padrão para transferência de dados.

### MODELOS DE CONTROLE

:building_construction:

- **Controle centralizado:** Um subsistema é o manda-chuva, tem controle sobre os outros (gerenciar a execução dos outros).
  
  - **Modelo de retorno de chamadas:** O controle começa na parte superior da hierarquia e passa para níveis inferiores (chamada/retorno). Aplicável a sistemas sequênciais;
    
    - ![](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/2022-03-17-21-51-07-image.png)
  
  - **Modelo gerenciador:** A diferença é que a única hierarquia que existe é esse sistema gerenciador, e todos os outros o utilizam.
    
    - ![](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/2022-03-17-21-50-50-image.png)

- **Controle baseado em eventos:** Cada subsistema pode responder por eventos/chamadas gerados por outros subsistemas ou do ambiente do sistema.
  
  - **Modelos de transmissão:** É um broadcast, o evento é transmitido para todos os subsistemas, e qualquer subsistema que puder manipular esse evento responderá a ele.
  
  - **Modelos orietados a interrupções:** Usado em sistemas de **tempo real**, quando ocorre um evento uma interrupção é lançada e o sistema já tem pré-definido o tratamento de cada interrupção, ou seja, já sabe para qual componente enviar para seguir o processamento adequado.
    
    - ![](/home/arthur/Documentos/Programming_Study/imgs/5_Periodo/2022-03-17-21-55-30-image.png)

---

# PADRÃO CAMADAS

:calendar: 11/03

## CONCEITO

:building_construction:

É uma forma de separar **fisicamente ou logicamente** os componentes de um sistema/aplicação distribuído.

**Divisão de responsabilidades.**

Exemplos: 

- Camada física = hardware, organização das máquinas, equipamentos, etc;
  
  - Container é uma camada lógica;

- Sistema operacional;

- Banco de dados;

- Modelo de dados ();

- Microsserviços;

- Visão;

- Barramento de serviços;

- Etc.

## PARTIÇÕES

Lorem Ipsum

## 1 CAMADA

baixa escalabilidade, se eu quiser comprar alguma coisa na amazon teria que ter uma linha ponto a ponto com ela para o acesso, um terminal só meu..... linha telefonica

## 2 CAMADAS

- ```Uso
  
  ```

- Separa os dados da aplicação, ou seja, a aplicação roda no cliente, e o servidor fica responsável pela manipulação dos dados através das requisições que recebe.

- Cliente servidor 2 camadas x Cliente servidor web

## 3 CAMADAS

- Nova camada para a aplicação no servidor, agora o cliente não precisa se preocupar com as versões, etc.

- AInda não é o suficiente para arquiteturas web/móvel;

## 4 CAMADAS

- Conexões TCP/IP com HTTO/HTML

- Web se torna uma camada

N camadas...

## CONCLUSÃO

:building_construction:

À medida que o número de camadas aumenta os sistemas ficam mais abertos e flexíveis...  
• Porém, ficam mais vulneráveis (menos robustos e seguros).  
• O crescimento do número de camadas proporcionou o desenvolvimento de aplicações distribuídas sofisticadas.  
• A interface de usuário evolui com a separação das camadas.  
• Pode-se aplicar o padrão Model-View-Controller a partir de 3 camadas.

Um conselho: construa uma arquitetura tão  
simples quanto seja possível, mas nunca se  
esqueça que ela deve atender às necessidades  
do negócio do cliente e que um dia toda  
aplicação vai precisar de manutenção.

---

# CLOUD COMPUTING

:calendar: 25/03

:building_construction:

## CONCEITOS

A arquitetura de microsserviços, por exemplo, conta com a nuvem (pelo menos) para a hospedagem dos serviços<mark>... olhar slide</mark>

- Modelo que permite o acesso, através da rede, a uma gama de recursos configuráveis de hardware e software, sendo alocados virtualmente por meio de provedores de serviços;

- Grande conjunto de recursos que podem ser dinamicamente escaláveis, ou seja, reconfigurados de forma fácil e acessível para aceitar cargas variáveis ao longo do tempo.

> Pode ser considerado um estilo arquitetural! Pois dirige a forma como aplicações distribuidas são modeladas e desenvolvidas.

- Existem os aspectos gerenciais e financeiros também, pelo fato de poder alocar os recursos somente quando necessário.

Usos comuns:

- asd

- asd

- asd

- asd



## TIPOS DE NUVEM

- **Pública:** 

- **Privada:**

- **Híbrida:**



## NÍVEIS DE ABSTRAÇÃO

- **Infraestrutura como serviço:** 

- asd

- asd