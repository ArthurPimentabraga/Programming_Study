---
title: Arquitetura de Computadores (PUC-Minas - 2º Período)
author: Arthur P. Braga
book: Organização estruturada de computadores - Tanenbaum
---

### General

**1ª Aula ->** Apresentação e falou o básico de arquitetura computacional, como arquiteturas x86 (mais antiga, 32 bits...) e ARM;

---

**2ª Aula ->** Continuação do slide || Unidade de controle (UC)!! || IAS || Bits e Bytes || Barramentos || Controladores || Pilhas

    Registradores: são memórias internas na CPU. (**Saber todos os nomes e tipos de registradores**)

    *Funcionamento do processadores, da memoria, e como os dados são registrados!!!*

---

**3ª Aula ->** Tabela ASCII || Software || Tradutores: Montadores e compiladores || Interpretadores || Sistema de numeração

- **Softwares:** programas que permitem o uso efetivo do computador;

- **Tradutores:** Interpreta e traduz o programa inteiro (conversão integral) de uma vez em linguagem de máquina. Ex: javac, C;
  
  - Vantagens: Execução mais rápida! || Uma vez traduzido, o código original pode ser descartado da memória, ficando somente o programa objeto e podendo executar o programa diretamente. 
  
  - Desvantagens: Não portabilidade do código executável entre as diferentes plataformas || Para ser utilizado o código precisa passar por muitos níveis de compilação || Processo de correção ou alteração do código requer que ele seja novamente recompilado.

- Montadores: 
  
  - Linguagem de montagem = Assembly || Montador = Assembler;

- Compiladores: A única diferença é o uso de linguagem de alto nível (Java, C#) em vez de linguagem de montagem (Assembly)
  
  **Compilação** (traduzir p/ linguagem de máquina), **Ligação** (ligá-lo a vários outros programas em linguagem de máquina dos quais ele dependa), **Carga** (Carrega-lo na memória principal) e **Execução** (Alocar o processador e transferir o controle dele para o programa a ser executado)

- **Interpretadores:** Lê e executa uma única linha por vez. Ex: Unix/Linux - Shell, Prolog, Lisp; 
  
  - Vantagens: A facilidade para executar comandos, a facilidade de depuração e mais flexíveis.
  
  - Desvantagens: Execução mais lenta do programa || Necessita sempre ser lido o código original para ser executado;

*Ciclo de instrução: Busca e executa. Saber interpretar uma instrução em hexa, por exemplo - Tabela OP CODE*

pergunta: O que seria exatamente o programa objeto gerado pelos tradutores? O programa já convertido para a linguagem de máquina, a linguagem alvo?

---

**4ª Aula ->** Conversão de bases || Introdução à sistemas lógicos (portas lógicas...) || Portas lógicas

---

**5ª Aula ->** Continuação de sistemas numéricos (*conversão e operações de bases*) **Conversão de nº decimais** || Sinal Magnitude || Complemento-2 (sinais positivos e negativos) || Padrão/formato IEEE 754

- Foram feitos os exercícios 1,2 e 3 de ARQ em aula
- **Exercícios 1, 4, 9, 12 ,13, 22, 23, 27 ctz que vai cair na prova (2,6, 7, 14, 24 talvez)(11 não cai)**

---

**6ª Aula ->** Abertura XII Scap

---

**7ª Aula ->** Continuação do Padrão IEEE 754 (32 bits) - Números PF: 32, 64 e 128 bits || 

---

 **8ª Aula ->** Circuitos Lógicos || Mintermos

---

### Meanings

- **Barramento:** É um **caminho elétrico** comum que liga e permite a comunicação entre dispositivos de hardware (processador, memórias, controladores...). Grupos funcionais dos barramentos: dados, endereços e controle; 

- **Registradores:** É uma combinação de *flip-flops* (variante de memória 1bit, amazena o valor de transição do bit, ou seja, de 0 para 1 ou vice-versa). Tal combinação permite armazenar valores superiores à 1bit. (memórias internas na CPU);

- **Controladores:** 

- **Pilhas:** É uma área de alocação de variáveis, ou seja, enquanto o programa está rodando ele empilha, armazena suas variáveis necessárias para execução de determinado processo neste local da memória, e quando o processo acaba este bloco da memória é desempilhado, desalocado; 
