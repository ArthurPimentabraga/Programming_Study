Notes

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
- Exemplo: Microsoft MS-DOS.

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
- Exemplo: Minix. Apesar de ter alguns exemplos ainda é dificil achar hoje. O kernel linux pode ser considerado como microkernel, mas para muitos essa definição não se aplica.

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

**Exonúcleos:** Em vez de clonar a máquina real, como nas VMs, outra estratégia é dividi-la ou dar a cada usuário um subconjunto de recursos. Divisão do hadware em vários kernels (núcleos) - Computação em nuvem geralmente é assim, a cada solicitação de criação de uma máquina, os recursos do hardware são divididos e parte dele é usado em cada nova máquina. 

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
  - Criar uma *thread* custa um pouco caro. Manter controle de todas ativas não é uma tarefa tão simples. Ter um objeto que gerencie isso ajuda muito, e com ele viabiliza usar *threads* de execução mais curta, já que o custo é minimizado por não ter que ficar criando e destruindo várias *threads*.
  - Thread pool:
    - Criar várias threads na inicialização e alocá-las em um banco;
    - Tarefas novas: “acordam” threads do banco;
    - Se há falta de threads: espera.
  - Agilidade;
  - Flexibilidade;
  - Controle de recursos.

#### Escalonamento de processos (e/ou threads)

Multiprogramação: muitos processos ou threads aptos a executar.

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
  - Soft real-time: quando os prejuizos são aceitável. Ex: Um jogo da uma travada leve.
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

First come, first served. Fila de processos. Bem simples, porém o ponto negativo é que não é justo, um processo relativamente pequeno pode demorar muito para ser executado, por estar no fim da fila por exemplo. Consequentemente uma vazão pequena.

- Tipicamente usado em sistemas em lote;
- Não-preemptivo.

##### SJF

Tarefa mais curta primeiro (**shortest job first**). Ordenar os processos pelo tempo de execução (trabalho necessário). Consequentemente a vazão aumenta. O problema é saber por quanto tempo o processo será executado :) Funciona melhor com tarefas previsíveis, ou seja, que dê para calcular um tempo previsto de processamento, tarefas específicas que são sempre executadas (pegar o tempo médio...).

- Também não-preemptivo.

##### SRT

Menor tempo restante (***Shortest remaining time***). Variação do SJF. na chegada de outro processo, é avaliado o tempo de execução do novo processo, se for menor que o tempo restante do processo atual, o escalona-dor interrompe o processo, e o novo processo começa a ser executado. Se o novo processo tiver um tempo maior, a fila é reorganizada (geralmente usando método de inserção).

- O problema é se começar a chegar muitos processos novos. Tem que tomar cuidado para não ficar no "Adiamento infinito" - *starvation*. Para isso pode ser feito o agendamento de tarefas longas (exemplo de política de emergência).
- Preemptivo.

#### S.Interativos - Prioridades

Nos sistemas interativos o objetivo é executar as tarefas mais **importantes** primeiro. Diferente dos em lote que o objetivo é finalizar os processos mais rapidamente. Logo precisamos definir prioridades.

- Preemptivo.

Simplesmente é atribuido um valor numérico ("etiqueta") a cada processo, para na hora da execução ser visivél qual é prioritário.

- Prioridades - Valores estáticos: regra pré-definida por fatores externos;
- Prioridades - Valores dinâmicos: em geral, modificados pelo SO para bom andamento do sistema.

##### Round-robin

Ou escalonamento circular. Esse algoritmo atribui a cada processo um tempo máximo para processamento: **quantum**. Ou seja, ao fim do quantum, o processo sofre preempção. Com isso conseguimos aplicar justiça ao nosso algoritmo.

- Tamanho do quantum: Responsividade x Desperdício. Um quantum grande pode fazer a resposta demorar, e um pequeno pode ser um desperdício pelo fato de ter que trocar de processo, e isso gasta tempo.
- Em consequência o quantum chega a ser insignificante, pois o menor processo sempre vai ser o que finaliza primeiro, logo todos os demais devem ser executados naquele tempo (tempo de execução do menor processo). 

*O retorno médio pode ser maior, porém o tempo de resposta é maior!* É a socialização do processador.

![image-20210402112416167](../../imgs/3_Periodo/image-20210402112416167.png)

##### Filas de prioridades

Precisamos de prioridades para os processos, logo é feita uma mesclagem de round-robin com prioridades. Processos com prioridades iguais são executados em round-robin, o resto segue na prioridade.

- Importânica + justiça.

---

## Aula 8 - 10/03

#### Exercício de fila de prioridades

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Fila_Prioridades.png" style="width:45%"><img src="../../imgs/3_Periodo/Sistemas_Operacionais/Resultado_Fila_Prioridade.png" style="width:%"> 

#### Sistemas de tempo real

Cenário ideial: processos homogêneos com eventos periódicos.

Antes de aceitar o processo precisa decidir se é possível escalonar em tempo real. Isso é calculado: 

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Calculo_Possibilidade_Escalonamento.png" style="width:55%">

##### Taxa monotônica - RMS

"Nada muda". Nesse algoritmo cada processo tem prioridade fixa relativa à sua frequência. *Frequencia = período/total*. Ou seja, quem for executar mais vezes, com um ciclo mais curto, tem prioridade.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Taxa_Monotonica.png" style="width:70%">

---

## Aula 9 - 15/03

#### Continuação - Sistemas tempo real

##### EDF

Prazo final primeiro (Earliest deadline first). A prioridade é quem vai encerrar primeiro. É dinâmico.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/EDF.png" style="width:55%">

##### RMS x EDF

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/RMFxEDF.png" style="width:55%">

RMS: Dependendo das cargas... por causa da prioridade, um processo ou outro pode perder prazo. *O calculo para decidir se vai executar um processo, ou nao, só diz se é possível executar ele, mas não garante o cumprimento dos prazos.*

Porém o EDF é mais complicado, exige mais do sistema...

#### Escalonamento em multiprocessadores

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Multiprocessador.png" style="width:55%">

**Multicomputadores**: CPUs estreitamente acopladas que não compartilham memória.

- Escalonamento "simples", pois cada CPU é independente, logo é só distribuir as tarefas;
- Tem que saber fazer o balanceamento da carga e distribuição de processos.

**Multiprocessadores**: Sistema de computadores no qual duas ou mais CPUs compartilham acesso total a uma RAM comum. 

- Questão bidimesional, qual processo? E em qual processador?
- Tem que gerenciar se os processadores vão processar tal processo de forma independente (um único processador pra ele), ou relacionado (mais de um processador para o processo).

Cenário "simples": 

##### Tempo compartilhado.

  - Considerar processos e threads como independentes;
  - Estrutura única de escalonamento;
  - Eventos e interrupções: uso do algoritmo escolhido.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Fila_Multiprocessador.png" style="width:70%">

Sobre o exemplo de cima:

- Simples e eficiente;
- Permite o balanceamento entre processadores;
- Tempo compartilhado em processadores;
- Porém, para essa eficiência toda os processos precisam estar independentes, se tiver dependência, perde um pouco de eficiência. 
- Porém 2, quando muda processos de processador, é perdido a cache, consequentemente eficiência. 

##### Escalonamento por afinidade

Força o aproveitamento de cache dividindo os processos por processador antes de começar a execução.

- Essa afinidade por ser manual (usuário) ou do algoritmo (SO);
- Cada CPU usa a regra do algoritmo definido.

---

## Aula 10 - 17/03

#### Continuação de multiprocessadores

##### Escalonamento por compartilhamento de espaço

Threads que se comunicam muito devem ser executadas ao mesmo tempo. Quando threads são inicializadas juntas, cada uma é alocada para uma única CPU. Inicialização deve esperar até que haja CPUs suficientes.

- Não preemptivo;
- Quant. de threads x nº de CPUs livres;
- FCFS para gerenciar fila de pedidos por CPUs

*Mais comum em servidores e em sistemas em lote.*

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Escalonamento_CompatilhamentoEspaco.png" style="width:55%">

Cada grupo equivale à um processo, ou seja, threads inicializadas juntas, que compartilham espaço de memória (buscam nos mesmos endereços) e são executadas em CPUs reservadas à cada uma.

##### Escalonamento de bando

Gang scheduling. Mistura escalonamento de tempo (round-robin) com escalonamento de espaço. 

- Evitar perda de desempenho por comunicação bloqueada.
- Escalonamento síncrono
  - Todos os membros do bando executam simultaneamente em tempo compartilhado
  - Todos os membros do bando iniciam e terminam ao mesmo tempo seus quanta
  - A cada quantum, todas as CPUs são reescalonadas

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Escalonamento_Bando.png" style="width:55%">

#### Comunicação e sincronização entre processos e threads

##### SO e cenário atual

Cenário comum: multiprogramação, tempo compartilhado, paralelismo real, multithreading.

- Colaboração 
- Dependência
- Concorrência de theads

##### CPI

Comunicação interprocessos. Comunicação e sincronização de acesso de processos a recursos são fundamentais para evitar problemas:

- Inconsistência de dados. Ex: Processo de débito e crédito na conta do banco ao mesmo tempo, com saldo inconsistênte no final;
- Dados usados em duplicidade.

*Regiões críticas > Condições de corrida > Necessidade de exclusão mútua.*

##### Condição de corrida

Quando dois ou mais processos compartilham recursos e o resultado final depende de uma ordem de execução.

**Região crítica:** Trecho(s) dos processos nos quais os dados compartilhados são acessados. Potencialmente perigosos.

**Exclusão mútua:** Mecanismo para garantir que, se um processo está em sua região crítica, outros processos serão impedidos de estar em suas regiões crítica.

Princípios da boa exclusão mútua:

1. Somente um processo pode estar na região crítica a cada momento;
2. Não se pode fazer suposições sobre velocidade e ordem de execução de processos (Lei de Murphy);
3. Nenhum processo fora da região crítica pode impedir outros processos de entrarem em suas regiões críticas;
4. Um processo não pode esperar indefinidamente para entrar em sua região crítica.

*Obs: 1 e 2 são obrigatórios, ou não funciona. 3 e 4 são desejados, ou teremos alguns problemas.*

##### Espera ocupada

Busy waiting. Sem ajuda ou interferência do SO. Não há estado de bloqueio nem chamadas de sistema. Processo que não pode adentrar a região crítica gasta o tempo de processador inutilmente até o fim do quantum.

Alternativa 1: Desabilitar interrupções antes do processo começar a executar, e habilita ao sair (ao finalizar).

- Não segue o 4º princípio (Espera indefinida);
- Segurança comprometida;
- Pode ser usado pelo próprio SO. Ex: Enquanto aloca memória, ninguém pede mais nada.

Alternativa 2: Variável de bloqueio. Usar variável boolean, enquanto ela for false, o processo fica em "stand-by", assim que ela ficar true o processo segue o fluxo.

O problema que essa lógica não funciona, porque o 1º processo pode fazer boolean = true antes de executar seu processo, e o outro começar a executar logo em seguida. 

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Variavel_Bloqueio.png" style="width:55%">

Alternativa 3: Alternância estrita. Variável controla quem tem o direito de executar naquele turno. A ação é de ceder a vez, não de tomar. Só no final da execução do 1º processo que essa variável muda seu valor para que o 2º comece a executar.

- Funciona, mas não garante desempenho;
- Bloqueio desnecessário. O sistema sempre vai executar no tempo do processo mais lento.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/BusyWaiting.png" style="width:55%">

---

## Aula 11 - 22/03

#### Sleep/Wakeup

Chamadas de sistema para que o processo peça a ida ao bloqueio. Vai dormir se o processo **depender** de outro recurso. Ou quando o sleep é por período, por um tempo pré-determinado. *Recurso provido pelo SO.*

É importânte pelo fato de não ocupar o processador!

##### Produtores e consumidores

Modelo clássico de CPI. É um cenário metafórico.

*Buffer: Área de memória limitada e compartilhada. Alguém coloca para alguem tirar.*

Produtores de itens (escrevem na memória) e Consumidores de itens (retiram na memória). Streamming é um exemplo, não precisa de uma grande quantidade de memória para ver tal filme, o sistema vai enviando os dados e a placa de vídeo vai lendo e retirando da memória ao exibir o filme. 

Basicamente o produtor libera a operação do consumidor, e vice-versa.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Produtor-Consumidor.png" style="width:70%">

Porém, essa única verificação - if(cont==0) - pode ocupar o tempo do *quantum* e não mandar o consumidor dormir na hora devida. Consequêntemente o sistema trava, vai chegar um ponto que ambos vão estar dormindo. Uma hora isso vai acontecer (Lei de Murphy).

#### Semáforos

Resolve o problema anterior. Variáveis especiais (de sistema) para controlar o número de sinais pendentes. Só permite duas operações indivisíveis (não tem como dividir a operação no meio, tem que começar e terminar): 

- Up (Incrementar o sinal);
- Down (Testar o sinal).

O semáforo é oferecido por meio de chamadas de sistema (essas operações são executadas assim). Ou seja, operação em modo kernel, e sem interrupções do sistema (detalhe que resolve o problema anterior).

Algumas linguagens de programação de alto nível o semáforo é disponibilizado por meio de bibliotecas. No caso do Java, o semáforo é controlado pela JVM.

Comportamento geral:

- Down: Tenta decrementar o contador. Se tiver 0 manda o processo para o bloqueio;
- Up: incrementa o contador e libera processos pendentes.

##### Mutex

Mutual exclusion é um semáforo simplificado: valores 0 ou 1 apenas. *Semáforo binário*.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Semaforo.png" style="width:70%">

##### Produtor/Consumidor com semáforo

Precisa proteger em três cenários:

1. Buffer cheio (produtor) - Produtor não pode executar;
2. Buffer vazio (consumidor) - Consumidor não pode executar;
3. Escrita/retirada do buffer (ambos).

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Mutex.png" style="width:70%">

É Eficiente e elegante (simples). Porém deve ser realizada com extremo cuidado, tracing e depuração de erros é muito difícil.

*Tracing: Logs para mapear bug.* 

---

## Aula 12 - 24/03

#### Monitores

Solução de alto nível de abstração, provida pela linguagem. Determina uma região como região monitorada, e que terá dados e códigos compartilhados por threads. Somente um processo pode estar ativo em um monitor em um instante de tempo.

Esquema geral:

- Variáveis de condição para controlar a espera;
- Dois sinais: wait e signal (libera a variável);
- Signal é sempre a última instrução do monitor.

<img title="pseudo-codigo" src="../../imgs/3_Periodo/Sistemas_Operacionais/Monitor.png" style="width:90%">

Diferente do Sleep/Wakup as operações de "dormir e acordar" estão no monitor, logo ele já controla tudo para você.

Em resumo:

- Garante uma exclusão mutua "automática";
- Solução simples;
- Menos probabilidade de erro, pela linguagem fazer o controle, e não nós;
- Mas depende da linguagem de programação, nem toda tem.

#### Problemas clássicos - CPI

São cenários que modelam problemas recorrentes em SO e outros sistemas de software.

##### Leitores e escritores

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Leitores-Escritores.png" style="width:70%">

Professor é escritor, e aluno é leitor.

Outro exemplo é uma reunião no teams. Uma tela compartilhada é manipulada pelo proprietário, e somente visualizada pelos outros da reunião.

Premissa para solução básica: Leitores novos podem entrar se já há um ou mais leitores. Escritores entram se os dados estiverem totalmente liberados.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Solucao-Semaforo.png" style="width:70%">

O problema é que para o escritor entrar, os leitores precisam abandonar, e isso não garante a execução do escritor, pois pode estar sempre chegando um novo leitor, e os dados nunca vão ser liberados. (Starvation)

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Solucao-PrioridadeEscritores.png" style="width:70%">

---

## Aula 13 - 29/03

#### Jantar dos filósofos

Metáfora para demonstrar a efetividade do uso de semáforos.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Jantar_Filosofos_Cenario.png" style="width:70%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Jantar_Filosofos_Ilustracao.png" style="width:70%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Solucao_Aparente.png" style="width:50%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/primary_code_jantarFilosofos.png" style="width:70%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/secondary_code_jantarFilosofos.png" style="width:70%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/tertiary_code_jantarFilosofos.png" style="width:70%">

1. Thinking = processando, executando;
2. Eating = Usando recursos compartilhados - Mexendo nos dados;
3. Hungry = Estado de espera. 

> Thinking >> Hungry >> Eating. Precisa passar pelo estado de espera para usar os dados.

Modelo para situações de competição por acesso exclusivo a recursos compartilhados. Ex: Uso de várias fontes de dados para gerar um relatório.

---

## Aula 14 - 31/03

#### Deadlocks

>  Cenário atual: Multiprogramação || Multithreading || Compartilhamento e concorrência por recursos
>  E alguns desses recursos são exclusivos, ou seja, há uma necessidade de sincronização e espera.

Situação na qual nenhum processo em um grupo consegue avançar, todos estão bloqueados, esperando. Ex: Programa congelado.

> A Legislatura do Estado do Kansas dos Estados Unidos da América aprovou um estatuto que decretou que “Quando dois trens se aproximarem um do outro em um cruzamento, ambos deverão parar completamente e nenhum dos dois deverá ser acionado até que o outro tenha partido”. Esse estatuto ilustra uma situação de *deadlock* ou impasse.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Deadlocks.png" style="width:80%">

Felizmente só ocorre deadlock quando as 4 coisas acontecem ao mesmo tempo:

- Exclusão mútua;
- Retenção e espera (hold and wait) - Um processo tem um recurso, outro processo tem outro recurso, ambos precisam do recurso do outro, mas ninguém sede;
- Sem possibilidade de preempção;
- Espera circular.

##### Prevenção de deadlocks

O SO tenta impedir pelo menos uma das 4 condições de ocorrência.

- Prevenir a espera circular: Protocolos obrigando uma espera linear.
  - Ex: Numerar os recursos e só permitir alocação ordenada. 
  - Fácil para o sistema, difício para o programador :) Logo ninguém vai querer programa para esse sistema. Ex: Windows phone.

Ou seja, prevenir o deadlock não da certo, é muito custoso, e acaba dando errado :)

##### Evitar os deadlocks

Não fiz nada para prevenir, ela pode acontecer, porém vou tomar atitudes para minimizar a chance de acontecer.

Conceito de **estado seguro** do sistema: SO pode alocar recursos a um processo se puder garantir que não acontecerá um deadlock, ou seja, descobrir se vai ter falta de recurso. Se for o caso, coloca o processo para dormir até ser seguro.

1. Alternativa: Usando grafos. Monta ele, e analisa. Se for perigoso, faz o fluxo explicado acima.
2. <img src="../../imgs/3_Periodo/Sistemas_Operacionais/Grafos_Alocacao.png" style="width:80%">

Na prática é muito complicado também.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Estado_Seguro.png" style="width:80%">

Ou seja, evitar deadlock também é muito caro, SO não vai fazer isso também.

##### Detecção e recuperação de deadlocks

Depois que acontecerem, tentar solucionar o problema causado por um deadlock. Destravar o sistema e recuperar o estado consistente.

Alternativas para recuperação:

- Se possível -> Suspensão e preempção do processo que está travado. Geralmente não da, pois não da pra parar algo no meio;
- Retrocesso (backtracking). Andar para trás, CTRL+Z do sistema até o momento anterior ao problemático;
- Eliminação de processos, matar os programas. E torcer para matar o cara certo. Ou vai matar quem chegou por último (fez menos coisas e é menos provável de ser o problemático), ou quem chegou primeiro (fez e ta usando muita coisa, mais provável de ser ele, porém vai ter que refazer muita coisa).

Ou seja, tudo isso pode custoso também :):

##### Algoritmo do avestruz

Linux e Windows utilizam. Enfia a cabeça na areia e finja que não há nenhum problema. O custo das alternativas para lidar com os deadlocks é considerado alto para o sistema. Confiam que o programador faz programas sem deadlocks (usando semáforos corretamente). Ou te avisa que o programa não ta respondendo e tu resolve o que fazer.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Algoritmo_Avestruz.png" style="width:50%">

---

## Aula 15 - 05/04

#### Dúvidas para prova

---

## Revisão

#### Pergunta 1

**O que é uma chamada de sistema? Qual a relação entre chamadas de sistema e execução em modo kernel?**

Chamadas de sistema são procedimentos disponibilizados pela API do sistema operacional para a requisição de serviços por parte dos usuários (programas). Somente no modo kernel é possível a comunicação com o hardware, logo é preciso uma chamada de sistema para o kernel executar (em modo kernel) a operação desejada. Por exemplo, alocação de memória, uso de periféricos, criação e finalização de processos, entre outros.

#### Pergunta 2

**Por que é necessário um bloco de controle do processo (PCB) para cada processo nos sistemas de tempo compartilhado?**

No sistema de tempo compartilhado é necessário que os processos sejam independêntes para uma boa eficiência. Logo, precisamos de um PCB para representar e armazenar todas as informações associadas a cada processo de forma independênte.

#### Pergunta 3

**Qual a diferença entre processos que estão em bloqueio e processos na fila de prontos?**

Processos que estão em bloqueio estão esperando "algo que não é dele", ou seja, ele tem algum impedimento, esperando algo recurso externo à esse processo para poder continuar sua execução. Processos que estão na fila de prontos já estão totalmente prontos para serem executados, sem nenhum impedimento.

#### Pergunta 4

**Escolha duas arquiteturas de sistemas operacionais e faça um resumo sobre elas, apontando vantagens, desvantagens e exemplos de uso de cada uma. (ou faça sobre todas, melhor ainda!)**

- Arquitetura monolítica: Estrutura única, masisa, a grosso modo é só o main. É executado um único programa em modo kernel, com uma coleção de rotinas (métodos). Se ta tudo junto e misturado, todas as rotinas estão sempre disponíveise visíveis para todos. A desvantagem disso tudo é que um grande bloco de código dificulta o entendimento e manutenção do sistema, e uma falha boba pode derrubar todo o SO. 
  - Exemplo: Microsoft MS-DOS.
- Sistemas em camadas: Divide o Kernel em camadas independentes, com funções específicas. Existe uma hierarquia entre essas camadas, e a comunicação entre elas depende da hierarquia. A vantagem é que essa hierarquia proporciona uma maior segurança. Por outro lado pelo mesmo motivo essa arquitetura tende a ser mais lenta, pois a comunicação tem que trafegar entre várias camadas para alcançar seus objetivos.
  - Exemplo: MULTICS - Deu origem ao UNIX. Hoje nenhum SO é inteiramente arquitetado dessa forma, geralmente esse tipo de arquitetura é usado como subsistemas.
- Microkernel: É um Kernel que executa só as funções básicas, é o kernel menor possível. A ideia é só é usado como modo kernel, ou seja, para comunicação com o hardware, as outras coisas são executadas como serviço. "Tudo terceirizado - User mode". Como alternativa para diminuir ao máximo o tamanho da parte principal do sistema, delegando o resto, deixando com os serviços (programas/utilitários/softwares). O sistema é composto em cima do microkernel.
  - Exemplo: Minix. Apesar de ter alguns exemplos ainda é dificil achar hoje. O kernel linux pode ser considerado como microkernel, mas para muitos essa definição não se aplica.
- Cliente/Servidor: Sistemas em rede. Variação de microkernel por ser a mesma ideia de delegar/distribuir as funções. Algumas funções vão ser providas pela rede, vindas de outro computador. Ou seja, temos os prestadores de serviço (servidores) e usuários de serviço (consumidores). Comunicação por meio de mensagens, entre as máquinas da rede (Client, Process server, File server...). Praticamente todo SI que usamos hoje é um cliente/servidor, pela "onipresença da rede". Sistema na web e computação em
  nuvem. 
  - Exemplos: Laboratório da PUC, Microsoft Teams, entre
    muitos outros.
- Máquinas virtuais (VM): Cópia exata do hardware, basicamente faz a tradução do hardware desejado, para o hardware "real" da máquina que está rodando. Tradicionalmente utilizada para possibilitar compatibilidade entre sistemas.
  - Exemplos: Java roda em um VM; Emulador; Muito utilizado em
    computação em nuvem.
- Exonúcleos: Em vez de clonar a máquina como na arquitetura anterior, esse sistema divide o hardware em vários kernels, da para cada usuário um subconjunto de recursos. 
  - Computação em nuvem geralmente é assim, a cada solicitação de criação de uma máquina, os recursos do hardware são divididos e parte dele é usado em cada nova máquina.

#### Pergunta 5

**O que é um sistema de tempo real? Quando dizemos que um sistema de tempo real é escalonável?**

Um sistema de tempo real é caracterizado pela necessidade de cumprimento de prazos, ou seja, possui restrição para a execução dos processos. Exemplo: Controle de sinais de trânsito, radas de aeroporto, entre outros. É muito comum em sistemas de monitoramento. Podemos dizer que a execução de processos nesse sistema acontece no tempo do "mundo". 

Antes da execução dos processos em um sistema de tempo real serem executados, é calculada a possibilidade de sua execução, para saber se é possível cumprir os prazos necessários daquele sistema. Logo, só é escalonável quando há previsibilidade do tempo de execução e chegada das tarefas, para que se possa determinar se o conjunto de processos pode ser executado, ou não no tempo previsto. Em outras palavras, determinar se o conjunto de processos é escalonável, ou não.

A soma dos requisidos de tempo real não podem dar mais que 1, pq se der mais não vai conseguir cumprir o prazo.

#### Pergunta 6

**Considere um sistema de tempo real com duas chamadas de voz de periodicidade de 5ms cada, com tempo de uso de CPU de 1ms por chamada, e um stream de vídeo de periodicidade 33ms com tempo de CPU de 11ms por execução. Mostre como ficariam os 3 primeiros ciclos de execução destes processos em um sistema usando RMS e EDF.**

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Resposta_Questao6.png" style="width:90%">

#### Pergunta 7

**Como threads podem ajudar um programa a executar mais eficientemente? Dê um exemplo, evitando os que já foram mencionados em sala de aula.**

Thread é uma forma de um processo dividir a si mesmo em duas ou mais tarefas que podem ser executadas concorrencialemente. Ou seja, dividimos as tarefas para serem executadas em threads diferentes, que por sua vez possuem seus próprios recursos, como registradores, pilhas... mas acessam os mesmo dados e recursos. 

Dessa forma podemos fazer com que vários processos sejam executados ao mesmo tempo, com compartilhamento e economia de recursos (apesar de ter um maior consumo de recursos de gerência). Como consequência de tudo isso, temos o ganho de tempo na execução dos processos. 

Exemplo: Os navegadores (browsers). Podemos fazer o download de vários arquivos e ainda continuar interagindo e trafegando entre as páginas da web enquanto esses arquivos estão sendo carregados.

#### Pergunta 8

**Aponte uma vantagem e uma desvantagem de cada abordagem para a implementação de exclusões mútuas:**

a) Alternância estrita

Essa abordagem funciona e é simples de implementar, porém não garante desempenho, o sistema sempre vai executar no tempo do processo mais lento, ocupando o processador de forma inútil.

b) Semáforos

 As únicas duas operações possível são executadas em modo kernal, e sem interrupções do sistema, ou seja, essas duas operações são indivisíveis, uma vez iniciada, ela é finalizada. É eficiente e simples de implementar, porém deve ser realizada com extremo cuidado, pois qualquer erro mínimo de lógica pode fazer o sistema não funcionar, além de ser difícil de fazer o tracing e depuração desses erros.

c) Monitores

Monitores são uma solução com um alto nível de abstração e providas pela linguagem, ou seja, basicamente nós determinamos uma região critica como região monitorada, e o monitor já garante uma exclusão mútua "automática", sem a possibilidade de erro lógico de implementação, pois a linguagem que faz esse controle. O ponto negativo é que depende da linguagem de programação, nem todas possuem monitores.

#### Pergunta 9

**Analise a descrição dos sistemas de software a seguir e relacione cada um dos sistemas a um modelo de comunicação interprocessos estudado, apresentando as características similares em cada caso.**

**a) A receita federal libera mensalmente um novo lote de restituição de imposto de renda. Cerca de 25 milhões de contribuintes têm interesse em verificar, via Web, se suas restituições foram liberadas.** 

​	Facilmente  identificamos  aqui  leitores  (contribuintes  que  querem  verificar  o  status  da  declaração)  e  escritores (servidores  da  receita  que atualizam  de  acordo  com  os  lotes).  O  ideal  seria  que,  na  data  da  atualização,  o  sistema  fique indisponível por um tempo para que os escritores possam atualizar toda a base de dados, sendo esta depoisliberada para os contribuintes. Não há problema em milhares de contribuintes consultarem seus dados simultaneamente.

**b) Para o cômputo do resultado das eleições, devem ser enviados ao servidor e somados ao resultado os resultados parciais de todas as seções eleitorais do país. Os eleitores, a imprensa e os próprios candidatos podem consultar o resultado em tempo real.** 

​	Podemos pensar, num primeiro momento, em outro problema de leitores (imprensa, candidatos, eleitores) e escritores (sistema atualizando o resultado da votação). Em algum momento, o resultado precisa ser bloqueado para consultaspara que o sistema de votação atualize o total recebido das seções eleitorais. Se cada seção eleitoral puder, por si só, atualizar o resultado, teremos  milhares  de  escritores.  Assim,  considerando  somente  os  processos  das seções  eleitorais,  podemos enxergar  também  uma variaçãodojantar filósofos:  as  seções  concorrem  com  algumas  seções “vizinhas”(totalização  porcidade ou estado, por exemplo) e concorrem também todas entre si para uma totalizaçãonacional, se for o caso.

**c) Um gravador de discos Blu-ray deve ler dados do HD do sistema a uma taxa tal que permita que a escrita no disco óptico seja feita sem interrupções.** 

​	Aqui  temos  um  clássico  de  produtor/consumidor. A  leitura do  discoproduzdados  em  memória  temporária,  os  quais serão  lidos  pelo  gravador  de  Blu-ray  para  gravar  o  disco (consumidor).  Neste  caso  em  específico,  o  ideal  é  garantir  uma memória  grande  o bastantepara  termos  um  bom  nível  de  confiança  de  que  o  consumidor  nunca  irá  bloquear:  se  isso acontecer, a gravação será interrompida e causará um erro, de acordo com adescrição do problema.

---

## Aula 16 - 12/04

#### Implementação prática de threads

Classe Thread do java :)

##### Sincronização de threads

É necessário tratar os cenários com disputa, concorrência de threads. Se dois consumidores quiserem, ao mesmo tempo, acessar os mesmos recursos e dados, vai dar pau.

Basicamente utiliza-se semáforo, monitores... 

---

## Aula 17 - 19/04

#### Gerência de memória

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Gerencia_Memoria.png" style="width:80%">

Gerência de trocas -> Ta usando muito uma variável específica, então o sistema joga para a cache, entre outros exemplos.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Tecnicas_gerencia_trocas.png" style="width:80%">

O SO para fazer qualquer coisa na memória, precisa de todos os tópicos acima, ou seja, depende do processador. 

##### Conceitos

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Conceitos_Gerencia_Memoria.png" style="width:80%">

- P = Pilha
- D = Dados 
- C = Código

Cada processo tem essas três áreas de forma independênte, cada processo só sabe dele mesmo.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Memoria-Fisica.png" style="width:80%">

Para um processo entrar em execução, ele precisa estar na memória principal, na memória fisica.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/MMU.png" style="width:80%">

A primeira coisa que o SO precisa fazer é o endereçamento de memória para começar a executar o procesos em algum endereço da memória principal. A **MMU** que faz a tradução, o mapeamento do endereço lógico para o físico.

#### Técnicas básicas - Gerência M. Principal

> Veremos que a evolução da gerência segue o mesmo caminho que aprendemos programação:
> 1. Utilizará uma variável base para a gerência;
> 2. Um vetor;
> 3. Uma lista;
> 4. Árvore/Hash

##### Monoprogramação

Somente um processo, além do sistema, executa por vez. E temos dois processos na memória (SO + 1 processo).

- Endereçamento simplificado: registrador de base -> Somar o valor da base ao endereço lógico

Exemplo: 

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Exemplo_Gerenica_MPrincipal.png" style="width:80%">

- Gerência simples, quase inexistente. Porém ineficiênte.

##### Partições fixas

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Particoes_Fixas.png" style="width:80%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Exemplo_ParticoesFixas.png" style="width:80%">

Se um processo não ocupa a partição por completo, de duas uma. Ou ele usa para expandir-se futuramente, ou aquela memória fica meio que perdida/atoa.  

###### Endereçamento

Cada processo terá:

- Registrador de base: marca o início da partição (processo) na memória principal;
- Registrador de limite: marca o tamanho da partição na memória principal. (quantos bytes para frente a partição vai usar).

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/ParticoesFixas_MMU.png" style="width:80%">

Proteção primeiro - Relocação depois.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/GerenciaParticoesFIxas.png" style="width:80%">

*Obs: Caso não tenha partição que caiba um determinado processo, o mesmo não será alocado. Ou seja, esse tipo de gerência pode desperdiçar muita memória :(*

###### Fragmentação de memória

- Externa: Entre um processo e outro (entre duas partições usadas) há memória que não conseguimos usar (partição livre que não conseguimos usar).
- Interna: Quando há memória dentro de uma partição utilizada que não será utilizado por mais ninguém.

*Obs: Em partições fixas pode ocorrer os dois tipos de fragmentação. Em partições variáveis, só da pra acontecer a fragmentação externa.*


---

## Aula 16 - 26/04

#### Continuação - Gerência M. Principal

##### Partições variáveis

As partições são criadas à medida em que são necessárias pelos processos. **Partições livres vizinhas podem ser unificadas.**

Para o cenário a seguir temos algumas alternativas: 

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Cenario_ParticoesVariaveis.png" style="width:80%">

###### Alternativa 1: 

Como são partições variáveis, é possível a relocação de processos para o processo *F* poder entrar. **Isso chama compactação de memória**:

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Alternativa1_ParticoesVariaveis.png" style="width:60%">

> Porém1: É necessário parar todos os processos para a relocação.
> Porém2: É necessário copiar byte por bype de cada processo para o endereçamento desejado. E isso pode levar tempo.

*Utiliários para limpar memória do sistema, além de retirar o lixo da memória, ele realoca todo mundo.*

###### Alternativa 2:

Fazer a troca de memória (**SWAP**). Nesse caso, a troca de um processo inteiro, ou seja, se não tem lugar pra um processo prioritário, retira um da memória (coloca em bloqueio), e coloca o prioritário na memória.

> Porém: Pode ocorrer a fragmentação externa, por não fazer a relocação de memória.

###### Endereçamento

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Gerencia_ParticoesVariaveis.png" style="width:80%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Estrutura_Lista_ParticoesVariaveis.png" style="width:80%">

*A leitura é mais lenta que nas partições fixas :(*

---

#### Paginação

Para fugir de possíveis fragmentações utilizamos a paginação. Nada mais é que os processos divididos em páginas lógicas de tamanho **igual** e **fixo**. Ou seja, divide um processo em N páginas de mesmo tamanho.

A memória principal é dividida em páginas físicas de tamanho igual ao das páginas lógicas. Chamadas de: *Molduras de memória* por ficarem vazias esperando encaixar uma página de dados la dentro.

> Página lógica: Páginas do processos (dados do mesmo);
> Páginas da memória principal onde os dados vão ser armazenados. 

*Os processos são carregados página por página.*

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Carregamento_Paginacao.png" style="width:80%">

-  Ainda pode ocorrer fragmentação interna, porém somente na última página, mas geralmente perde muito pouco. Ou seja, aproveitamento de quase 100% da memória principal;
- E não temos fragmentação externa, toda página lógica pode entrar em qualquer página física.

> Porém: A complexidade de endereçamento de páginas aumenta. Uma vez que o SO precisa encontrar a página lógica e física que ele quer (nº da página, posição dentro da página).
>
> Para isso precisamos de uma **tabela de páginas para cada processo.**

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Enderecamento_Paginacao.png" style="width:80%">

- Calcular o nº da página = endereço lógico / tamanho da página
- Deslocamento = endereço lógico % tamanho da página *(o deslocamento é "o quão pra frente" na página o processo está, ou seja, quantos bytes pra frentes ele está)*.

Agora para encontrar o endereço físico o processo tem uma tabela de suas páginas para referenciar cada localização na memória física:

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Calculo_EnderecoFisico.png" style="width:80%">

Esse rolê todo é o preço que se paga para resolver os problemas anteriores :) Tudo isso é feito de uma forma rápida (mais lento que os outros, porém ainda rápido). Geralmente, em um clock, é possível passar todo endereçamento de memória que precisamos. 

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Clock_Enderecamento_Paginacao.png" style="width:80%">


---

## Aula 17 - 28/04

#### Memória virtual

E se tivermos a necessidade de executar processos maiores que a memória principal? *R.: Será que precisamos de um processo inteiro em memória principal durante todo o tempo de sua execução? (Suponha um editor de textos...) Com certeza não!*

A ideia da memória virtual é essa, nunca usamos tudo do processo ao mesmo tempo na memória. Logo, já temos o processo dividido em páginas, então mantemos em memória principal **somente o necessário** para a execução dos processos em um **dado momento**.

> SO utiliza espaço em memória secundária (disco) para "complementar" a memória principal. Ex: **SWAP** do linux S2. Isso é uma memória virtual.
>
> Ou seja, é uma área reservada do sistema. Quando necessário, o SO faz a troca entre memória principal e memória virtual. (Execução de processos que excedam o tamanho da memória principal).

No exemplo a seguir, meu sistema tem reservado 2GB do disco reservado para, se precisar, ser utilizado  como memória virtual.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Exemplo_Swapfile.png" style="width:80%">

---

#### Algoritmos de paginação na memória virtual

##### Substituição de páginas

Em caso de uma página lógica não estar alocada em uma página física, e precisarmos alocar ela, se tiver página livre pode alocar em qualquer uma dessas páginas livres. Mas se não tiver, precisamos substituir uma página.

Ou seja, se acontece uma falta de página e não há espaço na memória principal, é necessário substituir uma página da memória principal. E para isso precisamos de uma **regra de substituição**. E um bom algoritmo faz a melhor escolha possível para a retirada de uma página.

###### Melhor escolha

Tirar uma página que nunca mais será usada :) O problema é saber qual página seria essa. E a única forma de saber isso, é essa:

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Ver-o-futuro.png" style="width:25%">

Logo, a alternativa é fazer um palpite levando em consideração os dados que temos agora.

**Simulação:** Simular diferentes regras a partir de uma sequência de acessos de referência. Ou seja, escrever diversas regras (algoritmos) com um cenário simulado, e comparar com um algoritmo ótimo (um algoritmo fictício que sabe todas as páginas que vão ser usadas e quando vão ser usadas), mas também utilizando o mesmo cenário. Dessa forma sabemos qual regra mais se aproxima do algoritmo ótimo.

###### Algoritmo 1 - FIFO

A primeira página a entrar será a primeira a sair. *Premissa: Quem entrou primeiro deixará de ser importante mais cedo.*

O problema é que essa premissa nem sempre ta correta, e pode ocasionar em várias faltas de página. Exemplo, atributos *static*.

###### Algoritmo 2 - NRU

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/NRU.png" style="width:80%">

Ou seja, retira a página mais antiga, a que foi utilizada a mais tempo.

Exemplo:

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Exemplo_NRU.png" style="width:80%">

*Legenda: 4 faltas de página.*

###### Algoritmo 3 - Segunda chance

Junta os dois último algoritmos:

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Algoritmo_SegundaChance.png" style="width:80%">

Porém essa lógica mexe na memória, e ficar realocando é ruim. Logo:

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/SegundaChance+Relogio.png" style="width:80%">

Ou seja, não realocamos as páginas para o fim da fila, só voltamos a verificar a medida que for executando. Exemplo:

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Exemplo_SChance+Relogio.png" style="width:80%">

Mesmo tendo acabado com o mesmo nº de faltas do último algoritmos, em uma grande escala pode ser mais benéfico. Sem contar que é bem mais rápido, antes tinhamos que procurar quem tirar, agora **é só retirar quem o relógio estiver apontando ou o seu vizinho.**

###### Algoritmo 4 - LFU - [Não funciona]

A página menos frequente utilizada (Least Frequently Used) sai primeiro. Contador de acessos a cada página: sai a que tiver menor contador. *Premissa: uma página pouco usada até o momento provavelmente será pouco importante no futuro.* 

> Essa lógica parece boa, mas não funciona nessa ideia básica.
> - Problema 1: Quem acabou de entrar tem chance de sair de cara por ter o contador ainda em 1.
> - Problema 2: Gasta memória por ter um contador.
> - Problema 3: Pra atualizar o contador, a operação gasta tempo do processador, enquanto ele tiver incrementando, ele poderia estar processando um processo, perdendo desempenho.

###### Algoritmo 5 - LFU com envelhecimento

Para resolver os problemas anteriores. Ele não vai contar quantas vezes a página foi utilizada. Conta intervalos de uso (simulação do contador real).

*Envelhecimento: tentativa de "esquecer" valores de acessos antigos. A página é importante se continuar sendo utilizada.*

- Uso do *bit R* para implementação. 

![image-20210503193149686](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210503193149686.png)

Dessa forma matamos os dois ultimos problemas, limitamos a memória, não gasta tempo incrementando contador...

Ou seja, vai envelhecendo, perdendo valor com o tempo.

Exemplo:

![image-20210503193615684](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210503193615684.png)

###### Existem 2 tipos de substituição:

- Algoritmos globais: Escolhem uma página de qualquer processo em memória principal para substituir. Verifica páginas do sistema como um todo.
- Algoritmos locais: Escolhem uma página do próprio processo em memória principal para substituir, ou seja, do proceso que teve falta de página. Ideia de conjunto de trabalho.

###### Conjunto de trabalho (working set)

*Algoritmo local.* Tenta prever o conjunto mínimo de páginas necessárias para que determinado processo faça seu trabalho. Exemplo: tal página precisará ser usada nos próximos 10s, logo ela irá fazer parte do conjunto mínimo de trabalho para que o processo seja capaz de fazer o que ele quer/está fazendo agora.

A estimativa é a partir de um intervalo de tempo passado, ou seja, somente as páginas utilizadas no último intervalo de tempo (igual ao que eu quero prever) são incluidas no conjunto de trabalho mínimo. Exemplo: Nos últimos 10s as páginas *1,5,8 e 10* foram utilizadas, logo para os próximos 10s elas fazem parte do meu conjunto de trabalho.

Se meu processo quer utilizar um página que não esteja na MP, ele "olha" para esse intervalo de tempo, e caso meu processo tiver alguma página fora desse intervalo, ela é substituida.

> Proteção de uma página do conjunto com **Bit L (lock)**. Todas as páginas que estiverem no intervalo vão ser protegidas com esse bit.

###### Algoritmo 6 - WSClock

Usa o conceito de conjunto de trabalho e método de implementação do relógio (lista circular). *Essa lista circular é, provavelmente, bem menor que a lista circular original, pois a original é usada para toda a memória, já essa é utilizada só para o processo.*

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Regras_WSClock.png" style="width:80%">

Se Bit M = 1, ele só marca a página "pronta para morrer", mas não é substituida de imediato, pois para ser marcada é necessário salvar seus dados em disco e isso demora, logo compensa mais procurar outra página mais pra frente com o Bit M = 0. Em outras palavras, ela está disponível para ser substituida, porém se tiver alguém melhor ainda para ser substituido, esse outro alguém é retirado. E outra, tem uma thread que quando o sistema tiver "menos coisas para fazer", ela passar verificando a existência de páginas marcadas setando o bit M delas para 0, e tais páginas, ou vão ser retiradas de uma vez da memória, ou ela permanece até ser a vez dela de sair.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/Execucao_WSClock.png" style="width:80%">

*Array [página, bit R, bit M, horário de uso]*


---

## Aula 18 - 03/05

#### Algoritmos de paginação na MV [Continuação]

---

#### Projeto do sistema de paginação

Antes do uso da paginação por parte do SO, seus projetistas precisam tomar uma série de decisões acerca de sua implementação e funcionamento.

- Algoritmo de substituição;
- Política de alocação (global ou local);
- Compartilhamento e limpeza de páginas;
- Tamanho das páginas;
- Informações armazenadas;
- Implementação da tabela.

:arrow_down:

##### Politica de alocação

Em geral, algoritmos globais têm melhor resultado, pois podem ter páginas de outros processos que não estão sendo usadas à muito tempo. Porém: 

1. Não é adequado em alguns cenários (ex: WSClock). 
2. A quantidade de páginas por processo pode gerar **thrashing**.

> **Thrashing**: é um problema que consiste em processos que com poucas páginas na memória começam a sofrer perdas ou faltas dessas páginas, o tratamento de falta de páginas geralmente é lento e consome recursos de processamento. Fazer/refazer paginação demora muito mais do que o simples acesso à memória, ou seja, se um processo começa a ocupar muitas páginas, outro processo começa a sofrer muitas faltas de página, e isso necessita de várias operações de paginação. Ou até mesmo quando acaba o quantum do processo que estava ocupando a memória, e é necessário fazer toda a paginação dos processos que foram retirados e estão com falta de página, e isso precisa ser feito rápido, mas são operações demoradas. Resumindo: perde desempenho.

Caso o sistema perceba que algum processo está causando thrashing, temos algumas soluções:

1. Aumentar o conjunto de trabalho daquele processo (caso seja um processo prioritário, necessite de mais páginas...). Ou seja, se ele tiver mais páginas no seu grupo, consequentemente gera menos faltas de página;
2. Priorizar um processo. Caso ele seja um processo prioritário, necessite de mais páginas... prioriza ele na memória para sair do estado de thrashing, termina logo e libera a MP para outros processos. *Estratégia muito usada pelo Linux.*;
3. Suspender inteiramente um processo (trocar), ou seja, jogar para a memória virtual, abrindo espaço na MP para outros processos. E quando outros processos terminarem, ele volta para a MP. *Estratégia muito usada pelo Windows.*

:arrow_down:

##### Compartilhamento e limpeza da páginas

Ainda pode ocorrer thrashing, logo temos algumas técnicas para evitar isso:

###### Compartilhamento

É natural que muitos processos utilizem algumas áreas de memória em comum (processo que querem fazer a mesma coisa). Exemplo: 

- Muitos usuários acessando o Canvas;
- Diversos programas enviando dados pela rede.

Esse compartilhamento parece natural, mas nem toda página é compartilhável. Códigos e **dados** não têm a mesma política de compartilhamento.

- Endereçamento de instruções e dados de forma separada: processos podem compartilhar **tabelas inteiras de páginas de dados**. Mas no caso de um algoritmo atuando num processo querer retirar páginas compartilhadas usadas por outro processo, isso precisa ser tratado.

###### Limpeza

Não é todo sistema que faz a limpeza das páginas igual ao WSClock, logo o sistema que não faz isso precisa implementar uma thread de serviço - daemon - de paginação, que roda periodicamente e seleciona molduras para uma lista de disponibilidade. Ou seja, pega aqueles processos "marcados para morrer" e grava os dados da página no disco, setando seu status para *disponível*. Tais páginas podem ser utilizadas novamente pelo fato de terem seus dados salvos, mas caso outra página precisar ser alocada, a substituição é feita. 

Os status podem ser *livre* (moldura sem página alocada) - *ocupada* (moldura ocupada por página sendo utilizada) - *disponível* (moldura ocupa, porém acessível para troca).

*A thread pode usar o mesmo algotirmo da substituição regular.*

:arrow_down:

##### Tamanho das páginas

- Páginas pequenas
  - Melhor aproveitamento da memória :blush:
  - Porém, leva à tabelas de páginas maiores (que gastam memória) :cry:
- Páginas maiores
  - Leitura mais eficiente do disco :blush:
  - Porém, lavem à mais fragmentação interna na última página :cry:

###### Proposta

![image-20210505212422599](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505212422599.png)

###### Informações armazenadas na tabela de páginas

A tabela tem mais informações do que a própria localização física e número da página. Informações necessárias para o algoritmo e para o sistema.

Exemplo de uma tupla na tabela de páginas:

![image-20210505213148150](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505213148150.png)

##### Implementação da tabela de páginas 

Simplesmente é um vetor com os registros, mas isso não é bom, não é muito performático, logo geralemente é implementado de outras formas.

![image-20210505213949395](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505213949395.png)

![image-20210505214233214](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505214233214.png)

###### Tabelas multiníveis

Árvore B+

![image-20210505214654643](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505214654643.png)

A vantagem é que só o índice fica na memória, o resto só ta na memória caso esteja sendo utilizado. Porém, demora mais para localizar a página.

###### Tabelas invertidas

É invertido, por que ao invés de procurar pelo índice, tu vai informar o valor, e ele te retorna um grupo de possibilidades, ai é só escolher um.

![image-20210505214948723](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505214948723.png)

![image-20210505215328471](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505215328471.png)

Usa uma tabela hash para a tabela da MP, e informa a hash da página que quero encontrar, se der colisão só tratar.

---

## Aula 19 - 05/05

#### Projeto do sistema de paginação [continuação]

---

#### Segmentação - Gerência de MP

A paginação tem um problema: 

![image-20210505215835568](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505215835568.png)

![image-20210505220032029](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505220032029.png)

> Cada "pedaço" do processo tem um idendificador.

![image-20210505220432524](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505220432524.png)

![image-20210505220532608](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505220532608.png)

##### Benefícios

Se aumentar a quantidade de armazenamento de um segmento, o resto não precisa ser recalculado.

![image-20210505221112451](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505221112451.png)

![image-20210505221152801](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505221152801.png)

Dados não são executados....

##### Problema

![image-20210505221756977](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505221756977.png)

![image-20210505221834218](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505221834218.png)

##### Segmentação x Paginação

![image-20210505221904517](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505221904517.png)

![image-20210505222116732](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505222116732.png)

![image-20210505222256891](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505222256891.png)

![image-20210505222316298](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505222316298.png)

![image-20210505222623291](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210505222623291.png)

A partir daí é só fazer o mesmo cálculo para descobrir a página, deslocamento...

---

## Aula 20 - 10/05

#### Sistemas de arquivos [M. secundária]

- Armazenamento de grandes quantidades de informações;
- Armazenamento não-volátil (longo prazo);
- Acesso simultâneo.

Arquivo de um recurso de software que não existe no hardware.

- Arquivos como sequência de bytes;
- Blocos de disco x arquivos lógicos.

Papéis do SO / Sistema de arquivos:

- Gerência de espaço livre;
- Armazenamento de blocos lógicos e localização posterior;
- Acesso concorrente.

E tudo isso da melhor forma possível.

> **O arquivo é uma abstração, uma sequência de bytes que usaremos depois.**

![image-20210510193208155](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210510193208155.png)

O usuário não precisa ser técnico em informática para saber utilizar arquivos, ou seja, fazer download, copiar e colar pastas, colocar arquivos dentro de pastas, renomeia um arquivo, deleta um arquivo...

:arrow_down:

##### Arquivos

De forma mais detalhada:

- Arquivo para o usuário
  - Abstração de dados reais, ou seja, mostra os arquivos da maneira mais leiga possível, mais fácil de ser manipulada e entendida possível.
- Arquivo para o programa
  - Dados estruturados. Ele precisa saber o que cada linha siguinifica, tira informações delas, precisa ler uma string, uma linha de texto entendível.
- Arquivo para o SO
  - Em geral, o conteúdo é indiferente, o SO não sabe se é um arquivo de música, foto... só um conjunto de bytes.

###### Nomes

São fundamentais para a abstração, igual às extensões. Em relação ao nome, cada sistema de arquivos terá sua regra de nomeação.

###### Tipos (para o SO)

1. Arquivos regulares ou arquivos de dados

   - Contêm informações do usuário;

   - São manipulados por programas aplicativos

   - Exemplo: arquivo de imagem, pdf... é do usuário, e os dados são exibidos pelo mesmo por aplicativos.

     > 

2. Arquivos executáveis

   - Quer dizer que estamos dizendo ao SO que ele pode usar aqueles bytes para serem processados no processados, e resultando na execução de um programa.

3. Diretórios

   - Arquivos do sistema para organizar arquivos de dados.

4. Arquivos especiais de bloco ou caractere

   - Usados para dar acesso a dispositivos

![image-20210510200801421](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210510200801421.png)

![image-20210510201621231](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210510201621231.png)

- Acesso sequencial (linha por linha);

![image-20210510201832047](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210510201832047.png)

Quanto mais atributos à definir, mais informações, porém mais trabalho para armazenar.

![image-20210510202857182](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210510202857182.png)

![image-20210510203852715](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210510203852715.png)

- Sistemas com grupos de usuário. Exemplo: Linux

![image-20210512210949614](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512210949614.png)

|      | 4        | 2         | 1             |
| :--: | -------- | --------- | ------------- |
|      | r = read | w = write | x = execution |
|      |          |           |               |
|      |          |           |               |
|      |          |           |               |

chmod = change mode

- Sistemas com listas de permissões

:arrow_down:

##### Diretórios

É um tipo de arquivo - arquivo especial do sistema. Com o objetivo de organização lógica dos arquivos no sistema, ou seja, basicamente seu conteúdo é um conjunto de referências à arquivos, é uma lista encadeada de arquivos. *Uma pasta dentro de outra pasta, é uma lista de lista.*

###### Estrutura hierárquica

Estrutura mais comum hoje. Utiliza-se **árvore genérica**:

![image-20210512212102045](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512212102045.png)

> Nome de caminha absoluto -> começa no diretório raiz. Exemplo:
>
> - /home/arthur/Documentos/aula1.pdf
> - \Users\arthur\Documentos\aula1.pdf
>
> Por esse motivo podemos ter nomes igual de arquivos em diretórios diferentes, pois a path absoluta é diferente (o nome completo é diferente).
>
> Nome de caminho relativo e diretório de trabalho.
>
> - Diretório atual
> - Diretório pai

###### Operações com diretórios

1. Criar
2. Apagar
3. Abrir
4. Fechar
5. Ler
6. Renomear
7. Link (atalho)
   - ![image-20210512213808995](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512213808995.png)
8. Unlink

Igual aos arquivos, só conseguimos fazer tais operações por que o sistema operacional implementou essas chamadas de sistema.

:arrow_down:

##### Implementação do sistema de arquivos

Primeira coisa que precisamos saber é que um sistema operacional pode controlar diversos sistemas de arquivos (para o SO, cada sistema de arquivos é *considerado* um disco diferente). 

Cada sistema de arquivos estará em uma partição de memória secundária. Exemplo: Dualboot (Linux e Win), cada partição terá seu sistema de arquivos.

![image-20210512214752425](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512214752425.png)

> *MBR = Master boot record -> identifica como e onde um sistema operacional está localizado para que possa ser inicializado (carregado)*.
>
> *Boot block -> Código base do SO para carregar o kernel.*
>
> *Super block -> É essencialmente os metadados do sistema de arquivos e define o tipo, tamanho, status e informações do sistema de arquivos sobre outras estruturas de metadados* 

![image-20210512215241111](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512215241111.png)

Arquivos são formados por blocos, não compensa ler byte por byte, logo lemos um bloco.

Super block -> tabela de descritores.

![image-20210512215527534](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512215527534.png)

![image-20210512215924664](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512215924664.png)

![image-20210512220103464](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512220103464.png)

##### Alocação de arquivos 

###### Alocação Contígua

![image-20210512221310143](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512221310143.png)

É rapido, mas é como se fosse o esquema de partições fixas:

![image-20210512221511118](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512221511118.png)

![image-20210512221707479](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512221707479.png)

Outra parte boa é a utilização dele para arquivos que não irão se modificar - **media de somente leitura** (cd de música, filme, arquivos de instalação...).

###### Alocação por lista encadeada com tabela de índice

![image-20210512222503701](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210512222503701.png)

Completamente inviável para o sistema principal, por ocupar muito espaço.

FAT não tem atributo de proprietário (todos tem acesso).

###### Alocação por nós-índice (i-node)

![image-20210517192418668](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517192418668.png)

sub-arquivo que contém a descrição do arquivo = Descritor

> Um descritor por arquivo, ou seja, uma linha para cada arquivo, e não uma para cada parte da memória. Um índice por arquivo.

![image-20210517192829941](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517192829941.png)

É mais demorado, mas economiza espaço. *Lookup = localizar todas "as partes" do arquivo.*

Flexível por índices indiretos. Usa qualquer posição que quiser, só registar no descritor.

EXT3 é i-node

---

## Aula 21 - 12/05

#### Arquivos [continuação]

#### Diretórios

#### Implementação do sistema de arquivos [continuação]

---

## Aula 22 - 17/05

#### Implementação do sistema de arquivos [continuação]

---

#### Projeto de sistemas de arquivos

![image-20210517193853022](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517193853022.png)

**FAT**

Usou 4KB do último bloco e sobrou 24KB no bloco, logo temos um desperdício de memória, fragmentação interna.

![image-20210517193056590](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517193056590.png)

Não é bom criar blocos muito grandes uma vez que o Tanenbaum fez uma pesquisa, e o resultado é:

![image-20210517194414823](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517194414823.png)

![image-20210517195137519](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517195137519.png)

O equilíbrio também é ruim, pois o aproveitamento seria menor que 10%.

##### Candidatos

- Setor
- Trilha
- Cilindro
- Tamanho da página de memória

#### Compartilhamento de arquivos

![image-20210517195828289](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517195828289.png)

![image-20210517200018568](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517200018568.png)

- Hard links (sistema i-node)

Compartilhamento real, dois lugares apontando para o mesmo descritor, para o mesmo arquivo. Nos descritores teremos propriedades de compartilhamento. Ex: Cont.Ref:  2, ou seja, duas referências para esse mesmo arquivo. Essa propriedade serve até para não apagar um arquivo fisicamente quando somente um dos usuários deleta o arquivo. 

![image-20210517200435562](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517200435562.png)

Um efeito colateral é que se o proprietário deletar o link, ele continua sendo o proprietário, e caso o usuário B não tenha permissões...

- Symbolic links

Criamos uma referência para o diretório do proprietário, ao invés de um link direto para o arquivo. Porém se o proprietário apagar o arquivo, ele será excluido fisicamente. Ex: Atalho do windows.

![image-20210517200758161](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517200758161.png)

----

#### Sistemas de arquivo com journaling

![image-20210517201314002](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517201314002.png)

Registra tudo que vai fazer antes de fazer. Depois que falar tudo oq vai fazer é que vai começar a fazer. Consequentemente é mais lento, porém mais seguro, pois se achar um problema no fluxo, ele trata o cenário.

Quando ele finaliza ele 

Dificuldades:

- Operações idempotentes
- Transações atômicas

!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!! estudar os dois tópicos acima

Exemplos:

- Windows: NTFS
- Linux: ReiserFS, ext3 em diante
- MaxOS: HFS+

![image-20210517202824026](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517202824026.png)

![image-20210517203001205](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210517203001205.png)

*A lixeira é um diretório especial do sistema, ou seja, mandar para a lixeira, é só mudar o diretório do arquivo.*

---

## Aula 23 - 19/05

#### Segurança

Segurança de computadores aplicada ao SO é de extrema importância. Dispositivos computacionais armazenam informações valiosas: Projetos comerciais, documentos legais, dados bancários, arquivos pessoais...

Proteção contra acessos não autorizados e acidentes (danos físicos...).

##### Complicadores

- Sistemas inchados e novas funcionalidades
  - Arquivos texto x documentos elaborados. Ou seja, temos aplicativos para visualizar/utilizar tais documentos, logo um software malicioso pode se passar por uma foto, por exemplo, para o SO *cair nessa* e executar o sistema.
  - Páginas web estáticas x aplicativos web
  - Práticas seguras x comodidade de execução. Ou seja, fazer as coisas de maneira segura é mais trabalhoso.
- Sistemas em rede e aplicativos em nuvem
- Dados compartilhados. *Para compartilhar dados, precisamos dar permissão para alguém, e podem tirar proveito disso.*
- Cultura dos usuários. Ou seja, no mundo digital, as pessoas não são tão meticulosas... ​Não são educadas para utilizar de forma segura.​ ​

##### Ameaças ao SO

| Meta              | Ameaça                                     |
| ----------------- | ------------------------------------------ |
| Confidencialidade | Exposição e acesso não autorizado          |
| Integridade       | Manipulação e alteração não autorizada     |
| Disponibilidade   | Falha ou ataque de recusa de serviços      |
| Privacidade       | Uso não autorizado de informações pessoais |

##### Segurança e mecanismos de proteção

- Segurança - Política de segurança (Planejado no momento do projeto do sistema)
  - **O que** proteger? De **quem**?
- Mecanismos de proteção
  - **Como** proteger de acordo com as regras de segurança?

##### Perda acidental de dados

Casos em que não foram ocasionados propositalmente, como um ataque, por exemplo.

- Catástrofes naturais

- Erros humanos

- Erros de software

- Erros de hardware

- Acidentes e backups

    > Cópias de segurança (backup)
    >
    > - Sistema de arquivos pode oferecer serviço de backup
    >
    > Decisões:
    >
    > - Total (todos os arquivos do SO) ou parcial?
    > - Completo ou incremental (guarda só o que foi modificado desde o último backup)? 
    > - Dados originais ou comprimidos (possível de dar problemas)?
    > - Cópia física (espelhamento) ou cópia lógica? *Na cópia física é copiado byte por byte. Na lógica copia o bloco armazenado, ou seja, se tiver fragmentação interna, ele copia também. :grimacing:* 
    > 
    > *O backup deve sempre ser feito em um disco ou local sem vínculo com o original. De preferência em outro local.*

##### Invasões

Ameaças às metas de confidencialidade e integridade.

- Invasões passivas (quebra de confidencialidade);
- Invasões ativas (quebra de integridade);
  - Invasões ativas e backup

*Não necessariamente um invasão é algo malicioso, pode ter quebras internas, como a visualização de áreas internas do sistema, por usuários que não deveriam ver.*

##### Passos para segurança em SO

Geralmente é implementada em duas fases:

###### Autenticação

Autorização do usuário para acessar o sistema.

Sistemas computacionais podem ter acesso restrito.

- Acesso físico. Ex: Funcionário tem acesso a um prédio do trampo dele. - Acesso à um celular.
- Acesso lógico. Ex: Acesso aos dados...

*Autenticar: certificar-se de que o usuário é quem ele diz ser. Teste de Turing :blush:*

:arrow_down:

**-- Senha --**

Identificar o usuário por **algo que ele sabe.**

>  O ponto positivo é que é **fácil de implementar** e de **entender e usar.** Porém, se outra pessoa saber sua senha, ele consegue acesso.

Armazenamento criptografado de senhas. E melhor ainda, criptografia de mão única, ou seja, não sabe o dado original, toda vez que tentar logar, vai criptografar a entrada e ver se o resultado é igual.

> A dificuldade é que a senha é totalmente dependente do usuário.

Senhas **"fáceis"** e ataque de dicionário. Basicamente o cara tem um arquivo com zilhores de padrões de senhas possíveis, e ele mescla com informações possíveis de serem a senha desejada:

- Sequencias de letras e/ou números
- Dados pessoais
- Palavras ou expressões conhecidas
- Nomes próprios: cidades, esportistas, artistas, etc.
- Senhas-padrão de fabricantes. Ex: admin admin :weary:

> O problema de senhas difíceis é que, quanto mais difícil, mais provável que o usuário esqueça ou não erre facilmente. 
>
> Obs: Pegar uma palavra chave e trocar algumas letras por caracteres, não é definição de senha "difícil". O bom mesmo era pegar uma frase :grin: e embaralhar os caracteres. Quanto mais entropia melhor.

Senhas e políticas de uso:

- Forçar regras de entropia
- Forçar mudanças periódicas
- Senhas designadas pelo sistema
- Senhas de uso único
- Senha e desafio. *O problema que o desafio, geralmente envolvem dados pessoais, e dados pessoais são muito públicos hoje em dia. Ex: Qual era o nome do seu cachorro.*
- Autenticação em dois passos
- Execução periódica de um verificador de senhas. Ex: O próprio SO roda um verificador para saber se algum usuário está com uma senha muito fácil.

:arrow_down:

**-- Tokens --**

*A thing serving as a visible or tangible representation of a fact, quality, feeling, etc.* Autenticar o usuário por **algo que ele possui.** Mesma ideia de fechadura + chave. *Associado à autenticação de dois passos, hoje em dia.*

Ex: Tokens bancários - Smartcard; Dispositivos + app token

:arrow_down:

**-- Biometria --**

Medição das características físicas. Autenticar o usuário por **algo que ele é**.

Cadastro biométrico: Característica variada (entre usuários) e constante (para uma mesma pessoa).

Nos últimos anos a biometria diminuiu seu custo. E expandiu, também, pela computação ubíqua, ou seja, até meu celular tem verificador biométrico.

Métodos:

- Comprimento de dedos
- Leitura de digital
- Análise de assinatura
- Análise de retina
- Reconhecimento facial

> Biometrica não é 100% seguro, pode dar falsos negativos, falsos positivos. Além de ter sim formas de burlar a biometria, só é mais difícil.

###### Proteção

- A partir da autenticação, controle das ações permitidas para aquele usuário.

*Um ataque pode se passar po um usuário para acessar como se fosse o mesmo.*

Também tem a aceitação cultural, ou seja, algumas formas de autenticação biométrica pode não ser bem aceita dependendo da cultura do local onde ela será utilizada.

##### Ameaças e ataques ao SO

Ameaças e ataques mais comuns a SO são bem conhecidos. O que vimos, geralmente, são variações de falhas exploradas, e variações de complexidade e potencial de dano.

Ataques internos (alguem de dentro) e externos (alguem de fora).

###### Ataques via código-fonte

Alguém interno (que trabalha no código) colocou *atalhos* no código fonte para facilitar o ataque.

- Bombas lógicas (só eu sei resolver o problema, logo precisarão de mim);
- Alçapão (trapdoor - atalho). Ex: Algum login, ou palavra chave escondida no código;

> Importância de revisão de código e auditoria de sistemas de software.

###### Ataques internos

1. Fake login (página parecida com o login original);
2. Requisição aleatória de páginas de memória principal ou blocos de disco.
   - Áreas disponíveis podem conter "lixo" útil.
3. Forçar o sistema com chamadas ilegais, incorretas e atitudes não recomendadas.
4. Estouro de buffer
   - Execução de código malicioso que tenta desviar o fluxo de execução para ganhar privilágios.
   - Em geral, possível em linguagens que não verificam limites de memória (por exemplo, C).

    ``` c
    void A() {
        char B[128]; /* reservar um buffer de 128 bytes */
        printf("Digite mensagem para log: ");
        gets(B); /* lê da entrada padrao para o buffer */
        writeLog(B); /* enviar string formatada arquivo de log */
    }
    ```

![image-20210526212653017](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210526212653017.png)

###### Ataques externos

1. Varredura de portas de rede
2. Ataque a serviços disponíveis
3. Malware - malicious software

---

## Aula 24 - 31/05

#### Entrada e Saída

Papéis do SO:

- Emitir comandos para o dispositivos
- Verificar interrupções
- Tratar erros
- Fornecer uma interface simples e de fácil uso

Exemplo: Habilitar e desabilitar o bluetooth do celular, é uma forma simples e fácil para o usuário. Ou seja, ele não precisa saber o que ta rolando por debaixo dos panos.

Para o SO ele só sabe o que fazer pq ele responde os pedidos de processos.

Os dispositivos emitem a entrada, o SO verifica os pedidos de processos de acordo com essas entradas, e após a execução o SO emite a saída.

Verificar interrupções de sistema.

##### Para cumprir esses objetivos

O SO vai precisar se organizar de alguma maneira:

1. Independência de dispositivo
   - Exemplo: Se queremos salvar um arquivo em um pendrive ou em um SSD, a única coisa que precisamos é escolher o lugar que queremos gravar, de resto o SO resolve pra gente.
2. Tratamento de erro
3. Leituras síncronas e assíncronas
4. Buffer temporário



![image-20210531202645993](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210531202645993.png)

> - Device-independent: vai fazer toda a verificação necessária para a operação que foi requisitada pela camada superior.
> - Device drivers: os hardwares podem ser diferentes, logo precisamos de drivers para a comunicação entre os comandos do dispositivo e o hardware. 

![image-20210602205813979](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602205813979.png)

> Cada dispositivo teá seu controlador respectivo. Exceto a alaca USB que é universal (*Universal Serial Bus* - transmite e recebe bytes). 
>
> Quanto mais específico for equipamento, mais importante é seu drive.

##### Dispositivos de E/S

A primeira coisa que o SO vai fazer é dividir os dispositivos em duas classificações.

- Dispositivos de bloco: recebem e enviam blocos de bytes.
  - Tipicamente, memória secundária
    - Discos rígidos (HD)
    - Discos de estado sólido (SSD)
- Dispositivos de caractere: recebem e enviam dados em fluxos de bytes individuais (stream de bytes).
  - A maioria dos dispositivos tem este comportamento
    - Teclados
    - Mouse
    - Monitores de vídeo
    - Impressoras - poderia ser considerado de bloco, mas sua comunicação é estilo produtor/consumidor.

:arrow_down:

###### Discos rígidos (HD)

Dispositivos mais tradicional de armazenamento secundário. *Operação mecânica e magnética.*

> Em dispositivos de menor porte, em franca substituição por discos de estado sólido.



![image-20210602212312044](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602212312044.png)

![image-20210602212433551](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602212433551.png)

![image-20210602212731359](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602212731359.png)

A imagem vista a cima ilustra a limitação que por muito tempo persistiu nos discos rígidos. *Muito pela física e mecânica.*

E a imagem à baixo é uma evolução, passou a ser dividido por blocos lógicos.

![image-20210602212938178](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602212938178.png)

![image-20210602213400876](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602213400876.png)

> O HD é mecânico, ou seja, tem uma agulha que passa pelas trilhas lendo e escrevendo, a agulha pecisa se "locomover", é uma operação mecânica, e isso gasta tempo. Sem contar que o disco precisa rotacionar para que a agulha chegue no endereço desejado (Latência retacional).



**Algoritmos de leitura em disco:** Se não posso melhorar a física, organizo para que o trageto da agulha e disco não seja tão grande.

A execução dos pedidos de leitura pode ser feita de maneiras diferentes pelo SO:

**FCFS**

Fazer a leitura na hora que ela chega.

![image-20210602214501278](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602214501278.png)

**Deslocamente mais curto primeiro (SSF)**

![image-20210602214528676](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602214528676.png)

E se continuam aparecendo requisições próximas, o que acontece com as extremidades? Dependendo do cenário pode resultar em *starvation* (vai morrer de fome, ninguém executa). Ou seja, esse algoritmo não da garantia de execução.

**Elevador** - Varredura

![image-20210602215133411](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602215133411.png)

Não da garantia de resultado, mas da garantia de atendimento.

###### Acesso direto à memória - DMA

Se a CPU precisar controlar a transferência de dados do disco para a memória, desperdiçará muitos ciclos de processamento.

DMA: *direct memory access*

- Técnica implementada com o uso de um controlador que tem acesso ao barramento sem depender da CPU.
- Transferência de dados dos dispositivos diretamente para a memória.

![image-20210602215928705](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602215928705.png)

- Funcionamento em *word-at-a-time* - copia dado por dado
  - Roubo de ciclos de CPU
- Funcionamento *burst-mode* - envia uma rajada de dados

###### Discos e memória secundária

Nomeação e independência

- F:\Dados\Aulas\SO\Aula12.pdf
- /home/usuario/dados/aulas/SO/Aula12.pdf

Operações de otimização:

- Leitura antecipada (prefetch) - Se o sistema percebe um padrão de uso, ele já lê o provável endereço desejado. O problema é que isso é chute, logo pode gastar tempo de leitura atoa.
- Escrita adiada (deferred write) - Mesma situação de cima, porém com escrita. Ele acumula pedidos de escrita frequêntes para escrever uma vez só um bloco maior de dados.
- Chamada de sistema *sync* - de tempos em tempos ele realiza as operações de leitura e escrita.

Buffer de memória do SO e do dispositivo - Primero os dados ficam salvos na memória do dispositivo, e depois vão para a memória..

**Desfragmentação:**

Executar o desfragmentador para organizar os blocos de memória

![image-20210602221913172](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210602221913172.png)

:arrow_down:

###### Discos de estado sólido (SSD)

Utiliza circuitos eletrônicos para armazenamento de longo prazo. *NAND Flash memory.*

Operações eletrônicas: mais rápida e sem deslocamentos. Não tem operações mecânicas. Na velocidade da luz :smile:. 

Acesso uniforme a dados: Qualquer posição da memória é acessada com o mesmo custo.

Potencial perda de confiabilidade após certa quantidade de utilização. Ou seja, depois de muita leitura e escrita ele vai "descanstando".

**Operação de re-escrita, apagamento e coleta de lixo**

Hoje o ssd é formado por páginas e blocos.

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/ssd1.png" style="width:80%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/ssd2.png" style="width:80%">

<img src="../../imgs/3_Periodo/Sistemas_Operacionais/ssd3.png" style="width:80%">

![image-20210607193031062](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210607193031062.png)

![image-20210607193315130](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210607193315130.png)

![image-20210607193325448](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210607193325448.png)

- Problema:

![image-20210607193626777](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210607193626777.png)

Exclui do sistema de arquivo, mas não do disco.

![image-20210607193947786](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210607193947786.png)

- Solução: TRIM -> Na hora que apagar do sistema de arquivos, ele envia para o driver do ssd informando q tais arquivos foram retirados do sistema de arquivos.

##### Dispositivos de caracteres

Transmite ou recebe do sistema byte à byte.

###### Teclado

Driver de teclado: faz o processamento de códigos de entrada (código do dispositivo). Cada drive de teclado tem:

- Tabela de codificação
- Idioma

Código de tecla x caractere x comando

- Eco no monitor: tem um caminho longo até a tecla digitada aparecer na tela.

Uso de teclas especiais

- Bit de tecla pressionada

Teclas multifunção 

###### Mouse

Driver do mouse: Detectar o deslocament ΔX e ΔY + o botão apertado (correspondência de movimento)

- Trackball
- Mouse óptico - Microcâmera que fica "tirando foto" e verificando a superfície que está, ai compara as fotos em sequência. Por isso a luz infra-vermelho, para ajudar na visibilidade.

> A sensibilidade do mouse é definida no drive, ele transforma os milimetros de deslocamento capturados pelo sensor do mouse em pixels. E o mesmo funciona para a velocidade do clique, para ser considerado um clique. *Um Mickey*.

Dizem que no futuro será um nicho, só para quem gosta. Principalmente pelo avanço do touch. (Eu não largarei o mouse :smile:)

###### Monitores de vídeo / GUI

Modelo WIMP - Janelas, ícones, menus, dispositivos apontador (window, icon, menu, pointing device).

Placa gráfica, resolução e memória de vídeo

- FullHD: 1920 x 1080 = 1,977M
- Sistema RGBA: 4 bytes = 7,91MB

Frequência de atualização: interpolada x prograssiva.

- 75Hz = 75 x 7,91MB = 593MB/seg

###### Relógio

Nome historicamente usado para este dispositivo, apesar de ter um comportamente de *temporizador.*

Relógio: dispositivo de bloco? De caractere? Nenhum dos dois, não é dispositivo de entrada e saída, só ta aqui por que tem um *driver*.

![image-20210607203306491](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210607203306491.png)

Driver de relógio: *timestamp* e manutenção da hora. A hora é feita com uma referência.

- UTC
- Fuso horário
- Época/momento de referência
- Bug do ano 2000 - para economizar espaço, todo mundo usada ano com 2 digitos, logo na virada do milenio o ano ficou igual à 00.
- Bug do ano 2038 (Y2K38)

Manutenção sem energia:

- Pergunta para o usuário
- Bateria para manutenção de hora sem energia
- Sincronização com um servidor de hora (NTP)

---

## Aula 25 - 02/06

#### Entrada e Saída [continuação]

---

## Aula 26 - 07/06

#### SSD

#### Dispositivos de caracteres

---

## Aula 27 - 09/06

