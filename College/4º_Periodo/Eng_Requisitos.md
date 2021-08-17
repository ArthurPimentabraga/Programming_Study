---
title: Engenharia de requisitos de software (Puc-Minas - 4º Período)
author: Arthur P. Braga
period: 2/2021
---

# Introdução

02/08 - 03/08 :watch:

**Software como produto/solução!**

**O que é requisito?** É definido como *uma condição ou uma capacidade com a qual o sistema deve estar de acordo*. Precisamos garantir a consistência entre os requisitos e a solução entregue, e para isso fazemos o gerenciamento de requisitos.

Gerenciamento de requisitos trata-se de uma modelo sistemático para:

- Identificar, organizar e documentar os requisitos do sistema.
- Estabelecer e manter acordo entre o cliente e a equipe do proejto nos requisitos variáveis do sistema.

**Construção de um software:** 1. Planejar - 2. Fazer - 3. Verificar - 4. Agir

"A aplicação de um **método sistemático, disciplinado e quantificável** ao desenvolvimento, operação e manuntenção de software; isto é, a **aplicação da engenharia ao software.**"

**Principais modelos de referência:**

- Processo Unificado da Rational/IBM (RUP)
- Corpo de conhecimento da Engenharia de Software do IEEE (SWEBOK)
- Áreas de processo de modelo de maturidade CMMI

## Problemas/Dificuldades no desenvolvimento

- Aumento da demanda por novos softwares;
- Demandas diferentes:
  - Softwares devem ser construídos e entregues mais rapidamente;
  - Softwares maiores e mais complexos.
- Documentação insuficiente;
- Falta de processos e métodos;
- Dependencia de **sistemas legados** que necessitam de modificações;
  - mas possuem código e/ou documentação ilegíveis ou inexistentes.
    - Manutenção difícil, cara e demorada de software já existente.
- Coleta de dados sobre produtividadade inexistente ou insuficiente;
  - Comprometendo as estimativas de prazo, esforço e custo;
  - não permitindo a avaliação de novas ferramenteas, técnicas e padrões.

---

# ICEI Talks - Eng. Requisitos (Google)

09/08 :watch:

> Note: Utilização de métricas para medir a aceitação e utilização do produto/funcionalidades. em produção, com o produto lançado. Porém, geralmente isso é mais benéfico quando se deseja lançar rapidamente para ficar a frente dos concorrentes, pois se der errado, e não tiver muita adesão, pode ter sido um gasto muito grande de tempo e dinheiro. 

### Etapas da criação de requisitos

- Elicitação: Entender a dor do cliente, entender o problema dele, *descobrir os requisitos do software*. (Design thinking)
  - *Sempre perguntar a dor do cliente, e não o que ele quer!* Se não, ficamos limitados ao que ele quer, não o que ele precisa.
- Especificação: Descrever, documentar os requisitos levantados no tópico anterior. 
- Análise: Analisar os requisitos documentados e procurar problemas, requisitos inclompletos, inconcistências, conflito entre requisitos, entre outros. 
- Validação: Validar tudo que descreveu com o cliente. Uma boa ideia é prototipar, ajuda ao cliente entender a proposta.

### Requisitos funcionais VS não funcionais

**Requisitos funcionais:** Funcionalidades que o software tem que ter, *o que o software tem que fazer*. Exemplo: Gerar relatório.

**Requisitos não funcionais:** Características de qualidade que  o software tem q ter, *como o software tem q fazer aquilo.* Exemplo: capacidade de suportar inúmeros clientes gerando relatório ao mesmo tempo.

---

# Processo de desenvolvimento de software

10/08 :watch:

*Forma metódica para se desenvolver um software (desenvolvimento e manutenção). Sequência de passos executados com um determinado objetivo.*

*Software como produto, como solução para uma necessidade negócio.*

<img src="../../imgs/4_Periodo/Eng_Requisitos/fabrica_software.png" style="width:80%">

#### Ciclo de vida de software

- É concebido a partir de uma necessidade;
- É desenvolvido e entregue a um cliente;
- Entra em operação, sendo usado dentro de um processo de negócio e sujeito a manutenção;
- É retirado de operação no final de sua vida útil.

Geralmente acaba pela tecnologia, com a manutenção que não vale a pena mais (muito cara talvez), ou ficou muito desatualizada e limitada (não atende as necessidades mais).

O ponto de partida para a arquitetura de um processo é a escola de um modelo de ciclo de vida, podendo ser eles:

- Modelo em cascata

<img src="../../imgs/4_Periodo/Eng_Requisitos/modelo_cascata.png" style="width:50%">

- Modelo em espiral

<img src="../../imgs/4_Periodo/Eng_Requisitos/modelo-espiral.png" style="width:50%">

> Métodos ágeis, como o XP ‒ Extreme Programming e o Scrum, geralmente não contêm elementos suficientes para se qualificarem como processos completos. Na prática, os processos deles derivados também utilizam alguma das variantes do modelo em espiral.

#### RUP 

*RUP - Rational Unified Process*

É uma metodologia que utiliza UML para ilustrar os processos. [O que é RUP?](https://www.treinaweb.com.br/blog/o-que-e-rup-rational-unified-process)

<img src="https://i1.wp.com/www.diegomacedo.com.br/wp-content/uploads/2012/01/rup1.png" style="width:100%">



