---
title: Sistemas Operacionais (Puc-Minas - 3º Período)
author: Arthur P. Braga
---

## Notes

Primeira aula do semestre ja começa com uma abertura de fogos de artifício com trilha de star wars. Então meu prof abre a cam com fundo de um cruzador espacial (star wars), depois muda pra um fundo de Mordor.

---

## Aula 1 - 03/02

#### Apresentação da disciplina

---

## Aula 2 - 08/02

#### Respostas das perguntas solicitadas

**Qual sua área preferida no Curso?** -> Tudo relacionado à desenvolvimento, e codificação. Ex: POO, BD, Testes, Segurança.

**Você tem experiência prévia com SO?** -> Não.

**O que é um Sistema Operacional?** -> Basicamente é a ligação entre o Hardware e Software, fazendo toda gerência de processos em execução, uso de memória para uma melhor performace... Além de possibilitar a utilização do computador através de uma interface gráfica.

**Como um sistema operacional atinge seus objetivos?** -> Se o objetivo for uma melhor performace, com o melhor uso do hardware disponível, então ele faz toda uma gerência de todos os processos em execução, pode alterar o uso de memória, entre outros. Por exemplo, se tiverem somente processos leves em execução o SO pode alocar parte da memória RAM livre para ser usada como CACHE acelerando a busca de dados. Outro exemplo e a utilização de SWAP, parte da memória secundária é usada como memória principal quando o uso de RAM chega em um limite. Entre outros exemplos. 

**Quais são os três principais componentes de um sistema computacional na arquitetura de von Neumann?** -> CPU; Memória; Instruções de entrada e saída.

**Quais tipos de memória você conhece? Quais são as características de cada uma?**  -> **Registradores:** Memórias internas na CPU. Armazena temporariamente as instruções passandas para a CPU antes de serem processadas (como uma fila). **Memória Cache:** está entre a CPU e a mamória principal. Ou seja, a CPU procura na cache antes de procurar na principal, por isso mais rápido acesso. **Memória RAM (Principal):** É um exemplo de memória volátil. Permite leitura e escrita, com armazenamento temporário. **Memória secundária:** Armazenamento de dados permanentes (não se perdem com o desligamento da máquina, por exemplo). Exemplos: HD, SSD, Pendrive...

**O que são IRQs ?** -> Um sinal de interrupção enviado do hardware ao processador para "chamar a atenção" do processador para a execução de algum processo em específico, por exemplo: caracteres digitados no teclado, movimentos do mouse, operações de leitura e escrita no HD, entre outros.

**Como funciona um HD / disco rígido?** -> De forma eletromagnética. O disco do HD é composto por trilhas (organização e localização dos dados no disco). Para o registro, a cabeça de leitura se movimenta até a trilha desejada e envia um sinal magnético para o disco, positivo ou negativo, que pode ser entendido como 0 ou 1 (bits).  Por isso pode ser considerado um processo relativimente lento, pois é mecânico, analógico.

#### Estrutura de um SO

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Estrutura-SO.png" style="width:60%"/>

- Software básico: Configurações (coisas básicas do sistema).

#### Conceitos básicos

- **SO**
  - Como *gerente de recursos*.
  - Como *máquina estendida*. Significa que ele te da algo além do hardware, exemplo: criar arquivos, receber dados da rede... Ele fornece um conjunto de instruções para os programas e /ou programadores para executar essas tarefas anteriores (Comandos java para ler arquivos por exemplo, ele manda um comando para o SO - O SO que converte para binário para se "comunicar" com o hardware). Ele também já fornece APIs do sistema, como o GPS do android.
- **Kernel:** é o núcleo do sistema operacional, responsável por fazer as interações de hardware e software. Executa as funções básicas de um sistema. É o SO em sí. Ele que aloca memória... Só ele que acessa o hardware!
  - **Funções básicas:** Alocar memória, ver disco rigido
- Execução em **modo kernel** (supervisor): Acesso total ao hardware. Operações que necessitam da comunicação com o hardware Ex: new (necessário alocar memória - só no modo kernel é possível)
- Execução em **modo usuário**: Acesso restrito ao hardware. Somente instruções lógicas e aritméticas do programa.
- **Transição modo usuário - modo kernel - modo usuário:** Switch entre os modos para fluxos que necessitam de cada um.

---

## Aula 3 - 10/02

#### Continuação de conceitos

- **Chamadas de sistema:** Procedimentos disponibilizados pela API do SO para request de serviços pelos usuários (programas -> programadores). 
  - API do windows -> Win32.
  - POSIX: padrão definido pela IEEE para a manutenção de compatibilidade entre sistemas.
  - Programas de sistema/utilitário (config. de rede, gerenciador de arquivos...) usam chamadas de sistema.
- Ambiente operacional = interface gráfica para o usuário final;

**Shell:** Interpretador de linhas de comando, comunica com o kernel para execução dos comandos solicitados;

*SO é como Sauron, faz tudo nas sombras, a gente só vê a interface gráfica.*

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Estrutura-Basica-SO.png" style="width:40%">

#### Arquitetura de SO

**Sistemas monolíticos:** Estrutura única, masisa, *a grosso modo é só o main*. É executado um único programa em modo núcleo, com uma coleção de rotinas (métodos). 

- Se ta tudo junto e misturado todas as rotinas estão sempre disponíveis e visíveis. 
- Manutenção e entendimento complicado.
- Uma falha boba pode derrubar o SO todo.

**Sistemas em camadas:** Dividir o Kernel em camadas independentes, com funções específicas.

- Existe uma hierarquia das camadas, para a comunicação entre elas.
- Pode ser mais lento por causa da hierarquia. O sistema é inteiramente escrito em camadas, logo a comunicação tem que trafegar entre elas sempre.
- Por outro lado a hierarquia proporciona segurança.
- Exemplo: MULTICS - Deu origem ao UNIX.
- Hoje é usado como subsistemas. Não é usado como o MULTICS mais, como o SO inteiro.

**Microkernel:** É um Kernel que executa só as funções básicas. É o kernel menor possível. 

- Só é usado como modo kernel. Para comunicação com o hardware.
- As outras coisas são executadas como serviço. *"Tudo terceirizado - User mode"*.
- Como alternativa para diminuir ao máximo o tamanho da parte principal do sistema, delegando o resto, deixando com os serviços (programas/utilitários/softwares). O sistema é composto em cima do microkernel.
- Muito dificil achar hoje, nem o kernel linux é definido como microkernel.

**Sistemas cliente/servidor:** Sistemas em rede. Variação de microkernel, por ser a mesma ideia de delegar/distribuir as funções. Algumas funções vão ser providas pela rede, vindas de outro computador.

- Prestadores de serviço (servidores) e usuários de serviço (consumidores). Ex: Lab da puc, Teams...
- Comunicação por meio de mensagens, entre as máquinas da rede (Client, Process server, File server...).
- Praticamente todo SI que usamos hoje é um cliente/servidor. pela "onipresença da rede". Sistema na web e computação em nuvem.

**Máquinas virtuais (VM):** Cópia exata do hardware.

- Tradicionalmente utilizada para possibilitar compatibilidade entre sistemas.
- Basicamente faz a tradução do hardware desejado, para o hardware "real" da máquina que está rodando.
- Emulador é uma VM. 
- Importância hoje: 
  - Java roda em uma VM :)
  - Necessidade de execução de múltiplos servidores;
  - Isolar servidores -> isolar falhas;
  - Computação em nuvem (lembrar da AWS).
- Exonúcleos: Divisão do hadware em vários kernels (núcleos) - Computação em nuvem geralmente é assim, a cada solicitação de criação de uma máquina, os recursos do hardware são divididos e parte dele é usado em cada nova máquina. 

---

## Aula 4 - 22/02

#### Diferença entre arquitetura Android - Linux - Win

#### Histórico resumido

- Multiprogramação e Time-sharing (slide)

---

## Aula 5 - 24/02

#### Continuação do histórico

Por que e o que desencadeou a evolução do TCP/IP e a rede?

#### Desafios atuais

- Compatibilidade: Compatibilizar dados. Linux mantem dados de uma forma diferente que o Windows, por exemplo. Outro exemplo: SO conversar com server (hoje utiliza protocolos de rede pra isso).
- Portabilidade: Um sistema ser capaz de executar em mais de um local (hardware). Ex: Android tem alta portabilidade.
- Abertura: Sistemas abertos são mais facilmente compativeis e portateis. Mais dificil fazer um SO conversar com outro fechado. Os protocolos de rede (TCP>>HTTP...), por serem abertos, possibilitam a grande escala de comunicação entre sistemas que temos hoje. Foi quase que necessário tais protocolos serem aberto para isso. 
- Escalabilidade: Capacidade de um sistema crescer.

---

## Aula 6 - 01/02

#### Processos

É um programa em execução. Programa é o código fonte, mas quando começa a executar ele começa a ser tratado pelo SO como um processo. *Para execução é necessário estar na memória principal.*

Conceito central de SO
- Execução de tarefas solicitadas pelo usuário;
- Tudo ocorre a partir de necessidades dos processos. Tudo gira em torno dos processos.

Estrutura básica de um processo na memória principal: 

1. Pilha: Os últimos passos do algoritmo são executados primeiro, ou seja, as "dependências", os métodos chamados em uma parte do algoritmo, é executada primeiro que a parte do código onde foi chamada; 
2. Dados; 
3. Código (parte mais baixa, ou seja o primeiro a ser executado).

##### Multiprogramação 

Em um sistema de multiprogramação a CPU fica se alternando entre a execução de vários processos. Uma das principais tarefas do SO, ele precisa gerenciar qual programa vai executar primeiro e por quanto tempo. Por mais que parece estar tudo sendo executado ao mesmo tempo, não está, só é muito rápido. Pseudoparalelismo ou Paralelismo em multiprocessadores (nesse caso também tem que decidir em qual processador irá executar).

- Controle simultâneo de diversas tarefas
  - Alternância por bloqueio e prioridade
  - Retomada de execução

##### Estados de um processo

- Ciclo de vida na gerência de processos (Boi psicodélico)

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/CicloVida_GerenciaProcessos.png" style="width:70%">

*Só vai para o bloqueio quando o processo "pede algo que não é dele", algo externo.*

##### Bloco de controle do processo (PCB)

Objeto de sistema para representar um processo. Armazena informações associadas a um processo:

- Estado do processo (Pronto, espera...);
- Registradores : contador de programa, acumuladores, ponteiro de pilha, base, limite e endereço de memória;
- Prioridade;
- Contabilidade (Tempo que passou no bloqueio, tempo de processado...).

Tabela de processos: Basicamente uma tabela hash de PCB, para na hora de precisar de algo ele localizar rapidamente.

##### Troca de contexto

- Multiprogramação, alternância e troca de contexto

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/TrocaContexto.png" style="width:70%">

##### Pseudoparalelismo

Parece que os processos estão sendo executados em paralelo, ao mesmo tempo, mas não é dessa forma que ocorre, há a troca de contexto, troca de processos em execução. E só parece estar executando ao mesmo tempo porque é muito rápido.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Pseudoparalelismo.png" style="width:70%">

#### Threads

Unidade básica de utilização/controle da cpu. É uma forma de um processo dividir a si mesmo em duas ou mais tarefas (multithread) que podem ser executadas concorrencialmente.

Modelo de processo tradicional: Fluxo de controle único -> monothreads.

Processo multithread:
- Divisão de tarefas em fluxos independentes;
- Pode realizar mais de uma tarefa concorrentemente, ou simultaneamente.

##### Qual sua importancia?

  - Responsividade (execução de vários processos ao mesmo tempo, muito importânte em jogos);
      - Compartilhamento e economia de recursos (compartilhamento/economia de código...). Por outro lado temos maior consumo de recursos de gerência (overhead);
  - Aproveitamento de arquiteturas multiprocessadas (vários núcleos de processamento, por exemplo);
  - Como consequência de tudo isso, temos o ganho de tempo;

*Exemplo 1: Editor de texto. Em single-thread, cada processo abaixo seria executado após a finalização do anterior. Com multithreads tudo isso trabalha de forma concorrencial.*

- *Usuário digita o texto;*
   - *Verificação ortográfica/correção automática;*
- *Formatação de páginas não visíveis;*
- *Cópias de segurança.*
  

*Exemplo 2: Servidor web.*

  - *Despachante;*
  - *Trabalhadores.*
    

*Exemplo 3: Save de arquivo, pode utilizar uma thread para ir salvando o arquivo aos poucos.*

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Thread.png" style="width:70%">

##### Modelo de threads no SO

- Processos leves (LWP);
  - ciclo de vida equivalente.
- Possuem contador de programa, registradores e pilhas próprias;
- Compartilham código e dados;
- Mais leves para criar e destruir.

---

## Aula 7 - 03/03

#### Implementação e gerencia de threads

SO deve decidir como gerenciar threads

- **Espaço de usuário (muitos para um).** Outras threads são implementadas pelo processo e gerenciadas por ele. O próprio executável gerencias as threads usadas por ele. *Ex: Java, Linux*;
  - Como consequência a gerência dos processos, por parte do SO, é mais simplificado;
  - Não necessita alternar de processo para trocar de thread;
  - Como quem cuida das threads é o processo, não há paralelismo de fato. Somente as threads internas desse programa.
  - Como o SO não reconhece as threads, ele pode bloquear um processo inteiro e todas suas threads mesmo quando alguma delas poderia executar.
- **Espaço do núcleo - kernel (um para um).** Cada thread do processo é associada a uma thread de kernel.
  - Maior concorrência, paralelismo real em multiprocessadores;
  - Maior consumo de recursos de gerência (overhead). Atraso na criação de uma thread, tabela de threads...
  - Paralelismo real: suposta melhora de desempenho;
  - *Importância de limitar o nº de threads possíveis: um software malicioso pode sair criando várias threads, usando todos os recursos, e derrubar o sistema.*
- **Hibrido (muitos para muitos).** Tenta resolver o problema de gestão com uma threadpool.
  - Thread pool:
    - Criar várias threads na inicialização e alocá-las em um banco;
    - Tarefas novas: “acordam” threads do banco;
    - Se há falta de threads: espera.
  - Agilidade;
  - Flexibilidade;
  - Controle de recursos.

#### Escalonamento de processos (e/ou threads)

Multiprogramação: muitos processos ou threadsaptos a executar.

Problema: Não há processadores/núcleos livres para todos.

Objetivo: Manter os processadores/núcleos ocupados e finalizar as tarefas o quanto antes.

##### Escalonador

Ou scheduler, decide quem será o próximo processo da *fila de prontos a executar*. O algoritmo de escalonamento segue regras para determinar as escolhas.

- Escalonamento **não-preemptivo**: Quando um processo em execução **não** pode ser interrompido pelo S.O. Ou seja, espera um processo acabar para começar o outro.
  - Menos custoso, porque: O processo retém a CPU - Sem decisão ativa do escalonador
- Escalonamento **preemptivo**: O S.O. pode interromper a execução de um processo. Ou seja, em uma tentativa de aumentar a vazão, ele pode interromper os processos e começar a executar outro, e assim vai.
  - O processo pode ser temporariamente suspenso - Decisão ativa do escalonador

##### Tipos de sistema

*Tudo depende do sistema de destino, seus objetivos!*

- Sistemas em **lote**: Os processos são processados em lote. Não há interação contínua com os usuários. Tarefas periódicas. Comum em computadores de grande porte.
- Sistemas **interativos**: Interação contínua com os usuários. Determinada solicitação tem uma resposta instantânea. Ex: Sistemas web em geral, equipamentos pessoais, IDEs, Teams (sincroniza audio e video sem parar)... 
- Sistemas de **tempo real**: Necessidade de interação, mas também de restrições de prazos. Ex: Controle de sinais de trânsito, radar de aeroporto, monitoramento no geral. *Acontece no tempo do "mundo"*. 
  - Hard real-time: Sistemas em que prejuízos (não cumprimento de prazo por exemplo) não são aceitáveis, o erro pode ser catastrófico. Ex: Controle de sinais de trânsito.
  - Soft real-time: quando os prejuizos, é aceitável. Ex: Um jogo da uma travada leve.
  - Tem como característica ciclos curtos.

##### Critérios/Objetivos do escalonamento

Se aplica em **todos os sistemas**!

- Justiça: Dar a cada processo uma fração justa da CPU;
- Política: Sistema deve cumprir regras estabelecidas;
- Equilíbrio: Todas as partes do sistema computacional devem estar ocupadas.

Se aplica em nos **sistemas em lote**!

- Vazão (Thorughput): Número de tarefas executadas por unidade de tempo;
- Tempo de retorno: Tempo entre submissão de um processo e seu término;
- Uso da CPU: Manter a CPU trabalhando o tempo todo.

Se aplica em nos **sistemas interativos**!

- Tempo de resposta: Tempo de resposta a um (primeiro) pedido;
- Proporcionalidade: Tempo de atendimento de uma requisição em relação à expectativa do usuário.

Se aplica em nos **sistemas de tempo real**!

- Cumprimento de prazos: Evitar perda de dados;
- Previsibilidade: Regularidade e tempo de execução de tarefas repetitiva. Disivão do processo em tarefas/threads com comportamento previsível.

---

## Aula 8 - 08/03

#### Algoritmos de Escalonamento - Em lote

##### FCFS

Fila de processos. Bem simples, porém o ponto negativo é que não é justo, um processo relativamente pequeno pode demorar muito para ser executado, por estar no fim da fila por exemplo. Consequentemente uma vazão pequena.

- Tipicamente usado em sistemas em lote;
- Não-preemptivo.

##### SJF

Tarefa mais curta primeiro (**shortest job first**). Ordenar os processos pelo tempo de execução (trabalho necessário). Consequentemente a vazão aumenta. O problema é saber por quanto tempo o processo será executado :) Funciona melhor com tarefas previsíveis, ou seja, que dê para calcular um tempo previsto de processamento, tarefas específicas que são sempre executadas (pegar o tempo médio...).

- Também usado em sistemas em lote;
- Também não-preemptivo.

##### SRT

Menor tempo restante (***Shortest remaining time***). Variação do SJF. na chegada de outro processo, é avaliado o tempo de execução do novo processo, se for menor que o tempo restante do processo atual, o escalonador interrompe o processo, e o novo processo começa a ser executada. Se o novo processo tiver um tempo maior, a fila é reorganizada (geralmente usando método de inserção).

- O problema é se começar a chegar muitos processos novos. Tem que tomar cuidado para não ficar no "Adiamento infinito" - *starvation*. Para isso pode ser feito o agendamento de tarefas longas (exemplo de política de emergência).
- Preemptivo.
- Também usado em sistemas em lote;

#### S.Interativos - Prioridades

Nos sistemas interativos o objetivo é executar as tarefas mais **importantes** primeiro. Diferente dos em lote que o objetivo é finalizar os processos mais repidamente. Logo precisamos definir prioridades.

- Preemptivo.

Simplesmente é atribuido um valor numérico ("etiqueta") a cada processo, para na hora da execução ser visivél qual é prioritário.

- Prioridades - Valores estáticos: regra pré-definida por fatores externos;
- Prioridades - Valores dinâmicos: em geral, modificados pelo SO para bom andamento do sistema.

##### Round-robin

Ou escalonamento circular. Esse algoritmo atribui a cada processo um tempo máximo para processamento: **quantum**. Ou seja, ao fim do quantum, o processo sofre preempção. Com isso conseguimos aplicar justiça ao nosso algoritmo.

- Tamanho do quantum: Responsividade x Desperdício. Um quantum grande pode fazer a resposta demorar, e um pequeno pode ser um desperdício pelo fato de ter que trocar de processo, e isso gasta tempo.
- Em consequência o quantum chega a ser insignificante..................

*O retorno médio pode ser maior, porém o tempo de resposta é maior!* É a socialização do processador.

##### Filas de prioridades

Precisamos de prioridades para os processos, logo é feita uma mesclagem de round-robin com prioridades. Processos com prioridade igual são executados em round-robin, o resto segue na prioridade.

- Importânica + justiça.

Simulador de escalonamento de prioridades -> gerenciador de empacotador de pedidos.

---

## Aula 8 - 10/03

#### Exercício de fila de prioridades

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Fila_Prioridades.png" style="width:45%"><img src="../../imgs/3_Periodo/Sistemas_Operacionais/Resultado_Fila_Prioridade.png" style="width:55%">

#### Sistemas de tempo real

Cenário ideial: processos homogêneos com eventos periódicos.

Antes de aceitar o processo precisa decidir se é possível escalonar em tempo real. Isso é calculado: 

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Calculo_Possibilidade_Escalonamento.png" style="width:55%">

##### Taxa monotônica - RMS

"Nada muda". Nesse algoritmo cada processo tem prioridade fixa relativa à sua frequência. *Frequencia = período/total*

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Taxa_Monotonica.png" style="width:55%">

