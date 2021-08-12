---
title: Redes de computadores 1 (Puc-Minas - 4º Período)
author: Arthur P. Braga
period: 2/2021

---

# Introdução

04/08

Com a evolução da tecnologia, nós vimos a necessidade de transmitir informações, dados para outros lugares. *Redes: Conjunto de computadores autônomos interconectados por uma única tecnologia.*

**Aplicações comerciais:**

- Compartilhamento de recursos;
- Comércio eletrônico;
- IOT;
- Conectividade.

**Aplicações residenciais:**

- Redes sociais e Entretenimento interativo;
- Conectividade (Alexa...);
- Trocas de mensagens;

## Modelos

### Modelo Cliente-Servidor

Comunicação hierárquica. Servidores com hardware diferenciado e com centralização de serviços. Os clientes fazem solicitações aos servidores, através de requisições pela rede (link pelo navegador...). *Faz uma requisição, e recebe uma resposta (protocolo HTTP).*

### Modelo Peer to Peer

**P2P - Par a Par.** Não existe diferenciação entre clientes e servidores. Comunicação não hierárquica. Os usuários são cliente e servidores, podendo atuar como ambos ao mesmo tempo.

## Tecnologia de Transmissão de Dados

### Redes Ponto a Ponto

Comunicação entre pares de máquinas individuais. Um pacote pode passar por uma ou mais máquinas até atingir o seu objetivo. Existem esquemas de roteamento que escolhe o melhor caminho entre os vários possíveis.

### Redes de Difusão

Canal único de comunicação compartilhado por todas as máquinas de rede. Mensagens são transmitidos na forma de pequenos pacotes e recebidos por todas as máquinas da rede. 

<img src="../../imgs/4_Periodo/Redes1/UDP-TCP.png" style="width:90%">

---

# Camada física

11/08 :watch:

*Transporte dos dados, na forma eletromagnética, através de um meio de transmissão (cabo par trançado, fibra...).*

## Fundamentos de comunicação

Geralmente os dados, inicialmente, não estão em um forma possível de transporte, então é necessário faer esse tratamento/transformação. Transformar em sinais eletromagnéticos.

> Note: Analógicos = forma contínua

Um sinal pode assumir uma de duas formas:

- Periódico: Tem um padrão que se repete dentro de um intervalo de tempo.
- Aperiódico: Não tem padrão, não se repete ao longo do tempo.

> Ao chegar no "marco 0", fala-se que o sinal completou 1 ciclo.
>
> ![image-20210811210915663](/home/arthur/Documentos/PersonalFolder/Programming_Study/imgs/4_Periodo/image-20210811210915663.png)

### Sinais analógicos

Sinais analógicos periódicos podem ser classificados como: **simples ou compostos**. 

#### Sinais simples (senoidal)

Uma onda senoidal (simples) pode ser representada por 3 parâmetros:

- Amplitude de pico:
- Frequência: F = 1/T e T = 1/F (Frequência é o inverso do período)
- Fase: 

![image-20210811212042116](/home/arthur/Documentos/PersonalFolder/Programming_Study/imgs/4_Periodo/image-20210811212042116.png)

- Comprimento da onde:

##### Domínios do tempo e da frequência



#### Sinais compostos



##### Largura de banda



### Sinais digitais

> Taxa de transferência = Taxa de bits.

#### Análise de Fourier



### Transmissão de sinais digitais



#### Transmissão em banda base



#### Transmissão em banda larga



## PERDA DE TRANSMISSÃO



### Atenuação



### Distorção 



### Ruído

