---
title: Rootkit
author: Arthur P. Braga
---

# What is

Rootkit é um pacote de softwares que asseguram e mantem a presença do invasor no computador comprometido. Com o intuito de dar acesso e controle sobre o alvo de forma furtiva, e muitas vezes gradativa. Ou seja, após a invasão é instalado um *kit* de programas/mecanismos que escondem o invasor do sistema comprometido, fazendo com que os sistemas de detecção não percebam sua presença enquanto consegue cada vez mais acesso e controle ao sistema, e alcança seu objetivo seja ele qual for.

> Obs: O invasor tem acesso ao computador alvo com privilégios de administrador (*root*). Ou seja, as operações e processos que esses programas fazem no computador comprometido é com privilégio de administrador, para que o sistema se engane achando que aquelas operações estão sendo feitas, realmente, pelo administrador do sistema. *Daí o nome rootkit.*

A instalação de rootkits na máquina alvo pode ser feita de várias formas, geralmente está associada à outras técnicas de invasão conhecidas. As mais comuns é utilizando um ataque de phishing ou engenharia social com trojans¹, ou seja, o proprio usuário instala o software malicioso de forma inconsciente, e uma vez dentro o malware começa a instalar o rootkit.

¹ Trojan ou Cavalo de troia, é qualquer malware que engana os usuários sobre sua verdadeira intenção. O termo é derivado da história grega antiga do cavalo de Troia enganoso que levou à queda da cidade de Troia.

# Types

Existem vários tipos de rootkits, cara um atingindo diferentes partes / níveis do sistema. Alguns podem funcionar em modo kernel - usado para alterar a própria estrutura do sistema -, ou agem na memória, em drivers, entre outros. Outros agem mais à nível de software, até desabilitando ou removendo por completo qualquer software antivírus ou anti-malware que esteja instalado no computador comprometido.

> Quanto mais ao nível do núcleo está um rootkit, mais grave e difícil é de detectar.

Alguns tipos mais comuns são:

1. Rootkits ao nível do utilizador

   asdasdsa

2. Rootkits de Kernel

   asdas

3. Rootkits ao nível do Bootloader

   asdasd

4. Rootkits de memória

   asdas

   Se sua memória está constantemente ocupada, mesmo com poucos processos em andamento, a resposta pode ser esse malware.

5. Rootkits de Firmware

   asdasd

# Examples



# How remove a rootkit



# Rootkit out of malicious context



# History

*Apesar de existirem há mais de um quarto de século, sob uma forma ou outra, os rootkits tal como os conhecemos hoje em dia surgiram em meados dos anos 90, com o aparecimento dos rootkits de UNIX e os vírus silenciosos do DOS. Os primeiros rootkits para o Windows foram detetados ao virar do século, sendo os exemplos mais notáveis o Vanquish, que guardava as palavras-passe das vítimas, e o FU, que funcionava em modo kernel e era usado para alterar a própria estrutura do sistema, e não simplesmente as formas de acesso.*

# Referências

https://softwarelab.org/pt/rootkit/

https://youtu.be/bvdSI6rnmG4

https://www.avast.com/pt-br/c-rootkit
