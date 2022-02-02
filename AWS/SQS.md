---
title: Simple Queue Service
author: Arthur P. Braga
---

## Geral

Com o SQS temos uma liberdade de configuração bem grande, da definição de retentativas de processamento à limite de espera por mensagem (podemos diminuir o número de request feitos por mensagem se estourar esse tempo). Podemos definir também atrasos na entrega de mensagens, etc.

## Listening

Se não quisermos que os consumers realizem requests para o pull das mensagens podemos criar um listening para que o mesmo fique escutando a fila. Para isso podemos usar [JMS](https://docs.aws.amazon.com/pt_br/AWSSimpleQueueService/latest/SQSDeveloperGuide/getting-started.html).

[Micronaut listen/subscribe to AWS SQS](https://codersingh27.medium.com/micronaut-listen-subscribe-to-aws-sqs-ebde42ad3e65)

## SQS & SNS

