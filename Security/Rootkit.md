---
title: Rootkit
author: Arthur P. Braga
---

# What is

Rootkit é um pacote de softwares que assegura e mantém a presença do invasor no computador comprometido. Com o intuito de dar acesso e controle sobre o alvo de forma furtiva, e muitas vezes gradativa. Ou seja, após a invasão é instalado um *kit* de programas/mecanismos que escondem o invasor do sistema comprometido, fazendo com que os sistemas de detecção não percebam sua presença enquanto consegue cada vez mais acesso e controle ao sistema, e alcança seu objetivo seja ele qual for.

> Obs: O invasor tem acesso ao computador alvo com privilégios de administrador (*root*). Ou seja, as operações e processos que esses programas fazem no computador comprometido é com privilégio de administrador, para que o sistema se engane achando que aquelas operações estão sendo feitas, realmente, pelo administrador do sistema. *Daí o nome rootkit.*

A instalação de rootkits na máquina alvo pode ser feita de várias formas, geralmente está associada à outras técnicas de invasão conhecidas. As mais comuns é utilizando um ataque de phishing ou engenharia social com trojans¹, ou seja, o proprio usuário instala o software malicioso de forma inconsciente, e uma vez dentro o malware começa a instalar o rootkit.

¹ Trojan ou Cavalo de troia, é qualquer malware que engana os usuários sobre sua verdadeira intenção. O termo é derivado da história grega antiga do cavalo de Troia enganoso que levou à queda da cidade de Troia.

# Types

Existem vários tipos de rootkits, cada um atingindo diferentes partes / níveis do sistema. Alguns podem funcionar em modo kernel - usado para alterar a própria estrutura do sistema -, ou agem na memória, em drivers, entre outros. Outros agem mais à nível de software, até desabilitando ou removendo por completo qualquer software antivírus ou anti-malware que esteja instalado no computador comprometido.

> Quanto mais ao nível do núcleo está um rootkit, mais grave e difícil é de detectar.

Alguns tipos mais comuns são:

1. Rootkits ao nível do utilizador

   Esse tipo de rootkit afetam somente o sotfware (motivo pelo qual é mais fácil de ser detectado). Eles substituem arquivos executáveis de programas usados com frequência pelos usuários, para que toda vez que o alvo utilizar o programa desejado com o executável manipulado, na verdade está dando acesso ao computador para o invasor. Isso tudo enquanto o usuário utiliza normalmente o programa. 

2. Rootkits de Kernel

   Como o próprio nome já dá a entender, esse tipo de rootkit ataca/atua no Kernel, no núcleo do sistema operacional. De forma furgiva consegue alterar as funcionalidades do sistema, adicionando o próprio código, dependendo do nível de acesso consegue alterar todo e qualquer sistema interno do sistema operacional.

3. Rootkits de memória

   Por atuarem na memória principal do computador, este tipo de rootkit não é permanente, ou seja, por atuar em uma memória volátil o malware é excluido assim que o sistema é reiniciado. Porém, ainda é muito perigoso, pois utiliza a RAM para disparar processos maliciosos que rodam em background no computador infectado. Sem contar que consome memória, logo afeta o desempenho do computador (um motivo para ser mais fácil de identificar).

# Examples

Um exemplo real do uso de rootkit, foi o ZeroAccess, que foi descoberto em 2011. Esse malware tinha infectado mais de 2 milhões de computadores pelo mundo. Era um rootkit de kernel, porém ao invés de modificar as funcionalidades do sistema operacional, o mesmo forçou os computadores à fazerem parte de uma botnet em escala mundial. Ou seja, os criadores desse malware tinham um "exécito" de computadores ao seu dispor, para fazer ataque DDOS, enviar span, espalhar vírus, entre outras formas de utilização da botnet. E apesar de várias tentativas para desativar o malware, ele continua ativo até hoje.

# How to detect a rootkit

Como citado anteriormente, os rootkits são software que estão em execução no computador infectado, e podem até estarem escondidos na memória RAM, lançando programas que estão em background no computador. Logo uma performance mais lenta, e memória RAM constantemente ocupado, mesmo não tendo muitos programas em execução, podem ser sinais de que um rootkit malicioso esteja instalado no computador. Até a “Blue Screen of Death” (tela azul da morte), se ocorrido com frequência, pode ser um sinal desse malware.

Pode-se detectar e até mesmo retirar um rootkit instalado na máquina com um bom anti-malware e/ou anti-vírus, mas em último caso formatar o disco rígido pode ser a solução.

# Rootkit out of malicious context

Um rootkit pode, e também não pode ser considerado um malware (software malicioso). Tudo depende de como será utilizado. Rootkit só é considerado um malware quando é destinado a fins ilegais, para algum ataque, ou invasão criminosa. Porém, há usos de rootkit que podem ser legalmente corretos, por exemplo:

O *Stalkerware* é uma classificação de rootkit com o objetivo de monitorar a atividade de alguém, ou controlar o conteúdo que a mesma consome. Esse tipo de rootkit é comercializado para pais, empregadores, entre outros. Porém, só é legal caso os envolvidos estejam de acordo. Sem contar que em vários países, tais práticas são ilegais, e não podem ser comercializados. 

# History

*Apesar de existirem há mais de um quarto de século, sob uma forma ou outra, os rootkits tal como os conhecemos hoje em dia surgiram em meados dos anos 90, com o aparecimento dos rootkits de UNIX e os vírus silenciosos do DOS. Os primeiros rootkits para o Windows foram detetados ao virar do século, sendo os exemplos mais notáveis o Vanquish, que guardava as palavras-passe das vítimas, e o FU, que funcionava em modo kernel e era usado para alterar a própria estrutura do sistema, e não simplesmente as formas de acesso.*

# Referências

https://softwarelab.org/pt/rootkit/

https://youtu.be/bvdSI6rnmG4

https://www.avast.com/pt-br/c-rootkit
