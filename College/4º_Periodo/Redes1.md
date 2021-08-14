---
title: Redes de computadores 1 (Puc-Minas - 4º Período)
author: Arthur P. Braga
period: 2/2021

---

# INTRODUÇÃO

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

# CAMADA FÍSICA

11/08 :watch:

*Essa camada fará todo transporte dos dados, na forma eletromagnética, através de um meio de transmissão (cabo par trançado, fibra...).*

Geralmente os dados, inicialmente, não estão em um forma possível de transporte, então é necessário fazer esse tratamento/transformação. Transformar em sinais eletromagnéticos.

## FUNDAMENTOS DE COMUNICAÇÃO

Os dados podem ser uma das duas seguintes formas:

- Analógicos: Forma contínua de ter essa informação. Apresentando um nº infinitamente grande de níveis de intensidade em um intervalo de tempo, ou seja, entre A e B pode assumir um nº infinito de valores;
- Digitais: Assumem valores discretos, ou seja, valores específicos, um nº limitado de valores definidos (geralmente em binário, 0 e 1).

Tanto um sinal analógico quanto digital, pode assumir uma de duas formas:

- Periódico: Tem um padrão que se repete dentro de um intervalo de tempo, e repete esse padrão nos intervalos posteriores.
- Aperiódico: Não tem padrão ou ciclo que se repete ao longo do tempo.

> Obs: Um ciclo é definido como um padrão da onde dentro de um intervalo de tempo (T). Exemplo: O sinal passa de positivo para negativo, e chega volta para o positivo.
>
> <img src="../../imgs/4_Periodo/Redes1/ciclo.png" style="width:30%">

### SINAIS ANALÓGICOS

Sinais analógicos **periódicos** podem ser classificados como: **simples ou compostos**. 

A onda simples é a forma mais fundamental (base) de um sinal analógico periódico (não pode ser decomposto em sinais ainda mais básicos). E o sinal analógico periódico composto é a combinação de diversas ondas senoidais.

#### SINAIS SIMPLES (ONDA SENOIDAL)

> Aplicações: Envio de energia elétrica de um lugar para outro. Sensores de portão... Não são muitos casos.

Uma onda senoidal pode ser representada por 3 parâmetros:

- **Amplitude de pico (máx)**: corresponde ao valor absoluto de sua intensidade mais elevada. É proporcional à energia que o sinal transporta (topo e fundo da onda).

- **Frequência**: medida em Hertz (Hz), refere-se ao nº de períodos em 1 segundo.

  - Período: quantidade de tempo (seg.) que um sinal leva para completar um ciclo.

  - F = 1/T e T = 1/F (Frequência é o inverso do período)

  - Como a frequência é a taxa de mudança em relação ao tempo, uma mudança em curto espaço de tempo significa alta frequência. E mudanças ao longo de esaço de tempo prolongado significa baixa frequência.

    <img src="../../imgs/4_Periodo/Redes1/frequencia.png" style="width:50%">

- **Fase**: descreve a posição da forma de onda em relação ao instante de tempo 0. Medida em graus ou radianos (360º corresponde a 2π radianos). Vai nos dizer o estado do início do 1º ciclo da onda em um intervalo de tempo (a quantidade de deslocamento). Exemplo: Podemos dizer que ela está defazada em 90º, ou em 180º, e por ai vai.

<img src="../../imgs/4_Periodo/Redes1/sinal_analogico.png" style="width:80%">

- **Comprimento da onda (λ)**: corresponde à distância que um sinal simples pode viajar em um período. Depende tanto da frequência, quanto do meio em que está sendo propagado. *Existe em qualquer tipo de sinal.*
  - **λ = c / f** = **c x T**
  - c: velocidade de propagação (valocidade da luz)
  - f: frequência

##### DOMÍNIOS DO TEMPO E DA FREQUÊNCIA

Como trabalhar com as duas grandezas, tempo e frequência, ou seja, podemos representar nossa onda de duas formas, nesses dois domínios diferentes.

> Note: No domínio do tempo consigo visualizar cada ciclo. No domínio da frequência a representação é mais simples, e mais fácil de representar várias ondas senoidais de uma vez.

<img src="../../imgs/4_Periodo/Redes1/dominios.png" style="width:80%">

<img src="../../imgs/4_Periodo/Redes1/dominios2.png" style="width:80%">

#### SINAIS COMPOSTOS

> Aplicações: É mais comum que as ondas simples para a transmissão de dados.

É uma combinação de ondas senoidais simples com diferentes frequências, amplitudes e fases.

Diferente dos sinais simples, o composto pode ser **periódico ou aperiódico**.

- **Periódico**: A decomposição desse sinal fornece uma série de sinais com frequências discretas;
- **Aperiódico**: A decomposição fornece uma combinação de um nº infinito de ondas senoidais com frequências contínuas. Ou seja, se eu não tenho padrão, posso ter um nº infinito de ondas com frequência contínua.

<img src="../../imgs/4_Periodo/Redes1/sinal_composto.png" style="width:80%">

<img src="../../imgs/4_Periodo/Redes1/dominios_sinal_composto.png" style="width:80%">

> Note: 3f significa que essa onda tem 3x a **frequência fundamental** (ou 1ª harmônica), sendo ela f. Ela é chamada de 3ª harmônica.

##### LARGURA DE BANDA

A largura de banda de um sinal composto é a diferença entre a maior e a menor frequência contida nesse sinal.

<img src="../../imgs/4_Periodo/Redes1/largura_banda.png" style="width:60%">

A diferença é que em um sinal periódico temos todas as frequências definidas, e no aperiódico temos as frequências contínuas.

### SINAIS DIGITAIS

> Taxa de transferência = Taxa de bits.

#### ANÁLISE DE FOURIER



### TRANSMISSÃO DE SINAIS DIGITAIS



#### TRANSMISSÃO EM BANDA BASE



#### TRANSMISSÃO EM BANDA LARGA



## PERDA DE TRANSMISSÃO



### ATENUAÇÃO



### DISTORÇÃO 



### RUÍDO

