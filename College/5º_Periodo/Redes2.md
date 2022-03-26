---
title: Redes de Computadores 2 (Puc-Minas - 5º Período)
author: Arthur Pimenta Braga
period: 1/2022
---

# INTRODUÇÃO

:calendar: 08/02

## EMENTA

- Projeto de redes locais e de longa distância: topologia, equipamentos e  tecnologias;

- Arquitetura de Infraestrutura de TI;

- Redes sem fio. Administração, gerência e segurança de redes TCP/IP;

- Virtualização. Computação em Nuvem. Comunicação entre dispositivos  inteligentes.

---

# UNIDADE 1

## VISÃO GERAL

:computer: virtual

## HIERARQUIA DE NEGÓCIOS

<img title="" src="../../imgs/5_Periodo/Redes2/2022-02-10-20-45-59-image.png" alt="">

## ARQUITETURA DE TI X INFRAESTRUTURA DE TI

Basicamente a arquitetura de infraestrutura de TI é o projeto, a ciência de projetar e fornecer soluções tecnológicas. E a infraestrutura de TI em sí é a **instância** dessa arquitetura, é o que vai suportar todo o fluxo e processamento, é o hardware e o software, os dados armazenados e a rede em sí.

## TIPOS DE ARQUITETURA DE TI

- **Arquitetura Centralizada:** Tudo que compõe seu sistema está centralizado em um um único lugar, em um datacenter. Tudo é comprado, suportado e gerenciado nele;

- **Arquitetura Descentralizada:** Como o próprio nome já diz distriuí o sistema, o processamento em vários lugares, em vários computadores, servidores e dispositivos. Talvez uma arquitetura baseada em microserviços, etc;

- **Arquitetura orientada a Serviços (SOA):** Modelo de arquitetura de software que funciona na lógica de SaaS, conhecido pelas estruturas modulares e focada na reutilização de componentes para acelerar a criação de novas soluções;

- **Peer-to-peer:** Ponto à ponto é uma forma de arquitetura descentralizada, pois divide o processamento em computadores interligados entre sí, sem um servidor central;

- **BYOD:** Basicamente é uma tendência que os colaboradores irão utilizar os equipamentos pessoais e se conectar aos sistemas da empresa, ao invés da empresa fornecer um pc lá;

- **Cloud:** Só lembrar de AWS, uma infra fornecida por alguém para seu negócio. Uma infra que virou software para quem deseja utilizar. Podendo ter centralizada, distribuída, etc.

---

## MODELO DE INFRA. DE TI

:computer: virtual

Modelo proposto por Sjaak Laan:

<img title="" src="../../imgs/5_Periodo/Redes2/2022-02-14-20-54-54-image.png" alt="" data-align="center" width="408">

Os processos das empresas são *suportados* pelas aplicações, que por sua vez, junto com os Middleware, os bancos de dados... tudo isso utiliza recursos da infra, como por exemplo, um database está armazenado em um servidor. 

Logo, a infra está ali para prover recursos com alta disponibilidade, performance e segurança para as aplicações que irão suportar os processos das empresas.

> **Middleware:** software que fornece algum tipo de serviço comum para as aplicações, como: Gerenciamento de dados, Mensageria, Autenticação, entre outros.

---

# REVISÃO DE REDES I

:calendar: 15/02

> Estudar essa parte pelo slide. Aqui só tem anotações.

**Computação ubíqua pervasiva:** Foi chegando no nosso dia a dia sem a gente "planejar", chegou de fininho. Ex.: Waze, iFood, Alexa, SmartWatch, Geladeira smart, etc.

**Computação ubíqua científica.** Ex.: Nanorobôs no sangue, etc.

Um **modelo hibrido** pode ser usado para solucionar problema geográfico, de latência. Por que tu pode ter as máquinas servidoras espalhadas geograficamente com um modelo P2P entre elas, e os usuários sendo os clientes.

**NPS:** analogia com Fat32 e NTFS só que em rede.

---

## DEMAIS ASPECTOS DE INFRAESTRUTURA

:computer: virtual

<img title="" src="../../imgs/5_Periodo/Redes2/2022-02-17-20-22-34-image.png" alt="">

---

## INFRA. NO CONTEXTO DE SOFTWARE

:computer: virtual

**Infraestrutura ágil** é considerada uma resposta ao um manifesto ágil, ou seja, criar uma infra, um conjunto de automações que permitem que façamos manutenções e modificações nos ambientes sem impactos na estabilidade e segurança (**Infraestrutura sob demanda**).

---

# UNIDADE 2

## TEMA 1: ENDEREÇAMENTO

### CONVERSÃO BINÁRIA / DECIMAL

:computer: virtual

Vai colocando aonde cabe o número decimal, da esquerda pra direita:

<img title="" src="../../imgs/5_Periodo/Redes2/2022-03-03-20-26-23-image.png" alt="">

---

### ENDEREÇAMENTO IPV4

:computer: virtual

*Protocolo de internet versão 4.*

É um identificador atribuído a cada máquina em uma rede IP. Possibilita a um host em uma rede comunicar-se com outro host de uma rede distinta e distante, e idependente do tipo de rede.

E ai podemos ver a importância de projetar, implementar e gerenciar um plano de endereçamento IPv4, pois permite que a rede opere de forma correta, ou seja, que não falte IPs para nenhuma máquina, ou que máquinas destinadas à um objetivo não fique no mesmo bloco de IPs que outras de objetivos diferentes, etc.

Cabeçalho IP:

<img title="" src="../../imgs/5_Periodo/Redes2/2022-03-12-16-10-56-image.png" alt="">

Cada endereço é representado por 32 bits divididos em 4 blocos de 1 byte.

Cada endereço pode utilizar a noteção decimal, binária ou hexadecimal. Ex.:

> 192.168.10.31
> 
> 11000000.10101000.00001010.00011111
> 
> C0 A0 0A 1F

**Tipos de endereços IPv4:**

- **Rede:** Endereço pelo qual nos referimos à rede, ou seja, é um endereço que não pode ser usado por uma máquina, os bits de host ficam com 0;

- **Broadcast:** Endereço especial usado para enviar dados a todos os host da rede (os bits de host ficam com 1);

- **Host:** Endereços designados ao dispositivos finais da rede (os bits destinados aos host ficam com qualquer combinação diferente das anteriores).

Geralmente os **3 primeiros blocos** indentificam em qual rede **local** o host está, ou seja, é um conjunto de ips destinados aos hosts.

O **último bloco** é o identificados de um **host específico** dentro daquela rede local, ou seja, de um equipamento específico, uma máquina, um roteador, etc.

> Note: Normalmente o último bloco = .1 é destinado ao roteador, e as máquinas ficam entre 2 e 254.

> Note: Até agora falamos em um divisão dos bits para rede e host, mas também podemos fazer uma divisão de rede, subrede e host.

##### MÁSCARAS

Mas como podemos saber de fato quantos bits são usados para rede, e quantos são usados para o host? A porção de definada pela **máscara!**

Ex.: 255.255.255.0 = 24 bits para indentificar a rede, e 8 para o host.

Para dividir essa porção já foi muito usado a divisão por classes, o que hoje não é tão usado mais:

<img title="" src="../../imgs/5_Periodo/Redes2/2022-03-12-16-38-54-image.png" alt="">

Número de possibilidades de IPs por classe:

![](../../imgs/5_Periodo/Redes2/2022-03-12-16-43-58-image.png)

Máscara default (em decimal):

![](../../imgs/5_Periodo/Redes2/2022-03-12-16-49-56-image.png)

#### REDES - SUB-REDES, CIDR E NAT

Um dos problemas dessa forma de divisão de redes por classes é o **disperdício de a endereços**, ou seja, se temos um escritório que só necessita de 5 máquinas, uma máscara do tipo C (a menor possível) ainda teria um desperdício de, aproximadamente, 248 endereços.

Para solucionar isso temos algumas formas de configurar a rede.

> Note: Sub-rede com CIDR e NAT não são "boas práticas", o ideal é migrar para o IPv6.

###### SUB-REDE COM CIRD

A ideia é subdividir uma rede (Ex.: 192.168.0.0), para obter "redes" com menos host.

![](../../imgs/5_Periodo/Redes2/2022-03-14-21-24-05-image.png)

Para entender como subdividir uma rede podemos definir alguns passos:

1. Defina quantas subredes deseja para descobrir quantos bits são necessários para representar essa quantidade.
   
   1. Ex.:

<mark>Ainda há desperdício</mark>

<mark>VLSM</mark>

Ao invés de quebrar as subredes com o mesmo numero de hosts, passamos uma mascara diferente para cada, subredes variáveis, cada uma terá o número de hosts adequado.

> Note: Só pra complicar a conta :)

Para dividir sub-redes -> calcular a mascara de cada "grupo" isoladamente.

1. Ordenar os grupos pela quantidade de host necessários;

2. 

<mark>Exemplo:</mark>

<mark>CIDR</mark>

Roteamento sem classe - conceito para facilitar o rastreamento de IP no mundo

###### NAT

Forma de 

###### IPV6

asdas

#### ESGOTAMENTO IPV4

Lorem Ipsum

---

### ENDEREÇAMENTO IPV6

:computer: virtual

Solução definitiva para o problema de escassez do IPV4.

- Menor cabeçalho permitindo uma leitura mais rápida dos pacotes. E mesmo com menos campos nele, há como utilizar campos adicionais para não perder as funcionalidades.

- Capacidade de criptografia.

- Mudanças no cabeçalho para facilitar mecanismos de qualidade de serviço (tratamentos diferenciados).

![](../../imgs/5_Periodo/Redes2/2022-03-24-19-47-12-image.png)

Agora temos **128 bits** para os IPs, logo a estrutura muda: Ao invés de ter 4 blocos de 8 bits, temos **8 blocos de 16 bits**. Mas para não ficar uma infinidade de 0 e 1, convertemos para hexadecimal, chegando em 8 blocos de 4 caracteres em hexadecial.

Exemplo:

![](../../imgs/5_Periodo/Redes2/2022-03-24-19-50-58-image.png)

<img src="../../imgs/5_Periodo/Redes2/2022-03-24-19-51-04-image.png" title="" alt="" width="275">

#### CARACTERÍSTICAS

- **Endereçamento Unicast Global:** permite a alocação de endereços IPs suficientes para cada dispositivo no mundo, sem a necessidade de NAT.
  
  > Para cada metro² do mundo temos mais de 1000 endereços disponíveis.

- **Agregação Global de Rotas:** permite a alocaçõ de redes IPv6 de acordo com a região geográfica, evitando o crescimento desordenado das tabelas de roteamento no mundo.
  
  - Análogo com o telefone. Ex.: +55 31 = Brasil MG.
  
  - Para o Brasil prefixo 280/12.

#### DIVISÃO DO ENDEREÇO IPV6:

Os primeiros 64 bits:

| 12 bits           | 20 bits  | 16 bits | 16 bits |
| ----------------- | -------- | ------- | ------- |
| Região do planeta | Provedor | Cliente | Subrede |

Os outros 64 são para identificar os equipamentos :)

#### CONVERÇÕES PARA REPRESENTAÇÃO

![](../../imgs/5_Periodo/Redes2/2022-03-24-20-06-38-image.png)

#### ATRIBUIÇÃO DE ENDEREÇOS

- Estática (Manual);

- Dinâmica com informação de estado (Stateful - DHCP - Automática);

- Dinâmica sem informação de estado (Stateless)

- ID de Interface com formato EUI-64 (a prórpia máquina passa esse endereço pra ela).
  
  - Para isso usa o endereço MAC.

#### TIPOS DE ENDEREÇOS IPV6

- **Unicast:** Endereços atribuídos em interfaces individuais;

- **Multicast:** Endereço IP representa um grupo dinâmico de hosts;

- **Anycast:** Mesma coisa do anterior, mas ao enviar um pacote, ele é enviado somente para a interface mais próximo.

---

## TEMA 2: CABEAMENTO

### CABEAMENTO ESTRUTURADO

:computer: virtual

Disposição organizada e padronizada de conectores e meios de transmissão para redes de informática e telefonia, de modo a tornar a infraestrutura de cabos autônoma quanto ao tipo de aplicação e de layout, permitindo a ligação a uma rede de: servidores, estações, impressoras, telefones, *switches*, *hubs* e roteadores.



Temos 7 subsistemas importantes para a estruturação de uma empresa:

1. **Entrada do edifício:** Conexão com o cabeamento da rua;

2. **Sala de equipamentos:** Onde vão estar meus servidores, etc:

3. **Sala de telecomunicações:** Sala que vai distribuir o cabeamento;
   
   1. 1 por andar.

4. **Cabeamento Backbone:** Ou cabeamento vertical, é a conexão das salas de telecomunicações com a sala de equipamentos (fibra);

5. **Cabeamento horizontal:** Cabeamento das salas de telecomunicações até as estações de trabalho (par trançado);

6. **Área de trabalho:** Onde o colaborador vai trabalhar na sua máquina;

7. **Administração:** Identificação de cada cabo/ponto, etc.

![](../../imgs/5_Periodo/Redes2/2022-03-24-21-05-22-image.png)

---

## TEMA 3: EQUIPAMENTOS

### EQUIPAMENTOS DE REDE

:computer: virtual
