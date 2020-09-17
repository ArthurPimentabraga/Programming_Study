---
title: Introdução à Sistemas Inteligentes (Puc-Minas - 2º Período)
author: Arthur P. Braga
---

# Unity 1

### What is

Um algoritmo pode ser considerado uma inteligencia artificial no momento em que começa a tomar decisões, baseado em dados, de alto nível. Por que se não todo algoritmo de tomada de decisão poderia ser considerado uma IA.

Existem 4 paradigmas que definem como uma IA pode ser criada e desenvolvida. Através deles o desenvolvedor é capaz de pensar quais tecnologias usar, quais problemas a IA irá resolver, etc.

- **Pensando Humanamente ->** É a tentativa de entender como a mente humana pensa, e raciocina, e passar isso para uma máquina;

- **Agindo Humanamente ->** Para fazer a máquina agir como se fosse uma pessoa usa-se uma abordagem de observação e imitação das ações humanas. Ou seja, a máquina entende que para tal pergunta, uma pessoa costuma responder tal resposta, por exemplo. 
  
  Para isso usa uma enorme montanha de dados para tal algoritmo aprender. Dependendo do dado uma IA pode se tornar até preconceituosa. É como se fosse uma criança aprendendo observando as pessoas agirem à sua volta;

*Teste de Turing -> Coloque uma pessoa para "interrogar", conversar por alguns minutos com uma IA. Se o interrogador não descobrir que é uma máquina, e achar que está conversando com outra pessoa, a IA passou no teste.* 

- **Pensando Racionalmente ->** É basicamente a tomada de decisão pela lógica. Ou seja, através da lógica o algoritmo vai pegar os dados que tem, "raciocinar", e entregar a decisão, a resposta mais lógica, mais racional, ou em outras palavras, a melhor decisão. 

        *Lógica é a chave para modelar o conhecimento - John McCarthy*

- **Agindo Racionalmente ->** O algoritmo vai seguir um protocolo racional para resolver determinado problema, independente se a resposta for humanizada ou não. Exemplos: Robô aspirador, se ele encontra um obstáculo através de seus sensores, ele muda de direção através de seus atuadores (motores no caso). Outro exemplo e um robô que resolve o cubo mágico, através da matemática ele calcula os movimentos necessários, sem usar intuição humana. E por fim, o Mars Rover, tal robô precisa agir de forma independênte, sem controle humano.

---

### Applications and techniques

##### Jogos Digitais

- **Estados finitos ->** Pacman, não é um exemplo de sistema inteligente, porque tem um padrão de comportamento dos fantasmas (estados de comportamento finitos);

- As dificuldades do jogo podem se **adaptar ao nível do jogador** para ter uma crescente dificuldade na mesma proporção que o jogador fica melhor no jogo 

- **Dynamic Scripting ->** O sistema cria uma série de "regras" (scripts) e testa os mesmos com o jogador, se determinado script teve uma resposta positiva, ele o usa mais vezes. Ex: Em um jogo de luta se o script de *atacar e recuar* quando o jogador está no meio da tela funcionar, ele usa esse script mais vezes (esse script ganhou pontos);

- **Previsão ->** O sistema pode estudar seus padrões de jogabilidade para, por exemplo, saber aonde você irá chutar no fifa.

##### Música

Possibilidades:

Descobrir quais musicas você pode gostar de ouvir || Reconhecimento de musica || Composição de musica (Uma IA já criou o final de uma sinfonia inacabada) || Você canta a musica e o app reconhece a musica || Até ajustar o timbre da voz do cantor para ficar afinado

##### Saúde

Sistemas para contribuir no diagnóstico médico || Monitoramento de paciente (sem precisar estar na UTI, por exemplo) || "Alerta" de epidemia || Visão computacional é muito utilizada para tudo isso (auxilia muito em laboratório também...)

##### Setor Financeiro

Análise do fluxo de caixa da empresa... para saber se ainda **gera valor**, se compensa continuar como sócio... (Técnica: Buy & Hold) || (Técnica: Day Trade) Comprar na baixa e vender na alta, ai tenta fazer uma análise para ver quando vai crescer e quando vai cair || Análise de risco de um cliente no banco, por exemplo

##### Transporte Aéreo

Aeronaves autônomas (Controle do pouso e decolagem) || Redução de custos (config de malha aérea...) || Atrasos e cancelamentos de voos (previsão de atrasos para tomada de decisão antecipada) || Conforto e atendimento (assistentes virtuais, reconhecimento facial para alinhar o passageiro com sua bagagem) || Segurança (Analisar dados de voo para prever situações criticas, identificar falhas no sistema...)

---

### Computação Evolutiva

Ramo que utiliza a evolução biológica para fazer uma evolução computacional.<img title="" src="file:///home/arthurbraga/Documentos/Programming_Study/imgs/algoritmoGenetico.png" alt="">

### Aprendizado de máquina

- **Online:** A IA está aprendendo enquanto faz uma tarefa. Por exemplo: um carro autonomo está "dirigindo" e encontra um pedestre atravessando fora da faixa, e após isso diminui sua velocidade;

- **Offline:** Aprende e depois vai para o funcionamento. Aprende com dados primeiro;

- **Supervisionado:** Aprende com exemplo, ou seja, "treina" a IA com base em um conjunto de dados. Desse modo é possível ela analisar os padrões de comportamento para fazer previsões, por exemplo. O problema é que nesse modelo a IA fica limitada a esses dados, e a um cenário onde há algum tipo de padrão. Por isso a importância de escolher o modelo certo para o cenário certo.
  
  - Criação de modelos -> Uso dos modelos -> Sistemas inteligentes

- **Não supervisionado:** E se não houver padrões? Ai pode ser usada a técnica de recompensas (freedbacks), ou seja, a IA faz determinada ação e se aquilo ajudou, se foi positivo ela recebe esse feedback para fazer isso com mais frequência. Ex: O robô aspirador, se em um local da casa estiver mais sujo todos os dias, ele vai passar la com mais frequência.

Técnicas de aprendizagem: Matemática e Estatísticas - Rede Neural - Deep Learning (conjunto de redes neurais) 

---

### Agentes Inteligentes & IA na Sociedade

*O objetivo direciona a racionalidade - agente racional percebe e age sobre o ambiente.*

O **agente** percebe o mundo, através de sensores, e produz uma ação através de atuadores.

**Exemplo de sensores e atuadores:** Em um programa de diagnóstico médico, por exemplo, o sensor seria o teclado, por onde o médico entraria com os dados, e o atuador seria a tela do computador exibindo uma mensagem na tela.

**Sistemas de regras - Exemplo**: se a água do chuveiro estiver muito fria -> aumentar a temperatura

##### Tipos de agentes

- Agente reativo -> tabela de regras (if else - regras definidas);

- baseado em modelo -> armazena o modelo probabilisco no agente para ele tomar a decisão mais adequada. Ou seja, passa as informações pra ele, e o mesmo decide qual a melhor ação baseada nessas infos;

- Baseado em objetivo -> É definido um objetivo para o agente e ele tomará decisões, escolherá suas ações para alcançar tal objetivo;

- Baseado em utilidade -> Você não sabe onde quer chegar (não tem objetivo fixo), mas tem uma medida de performace das ações do agente. Ex: quero que meu drone economize energia nas ações e tarefas que ele realize. Dessa forma ele faz de tudo para economizar energia, como procurar um caminho mais curto, que evite obstáculo...

- Sistema multiagente -> agentes comuns mas que podem se comunicar. Dessa forma os agentes podem se coordenar para atingir um objetivo em comum com maior eficiência, por exemplo.

*Pode combinar os tipos de agentes no seu sistema*

---

### IA na Sociedade

##### Democratização da IA

APIs :)

**Na sociedade ->** Como a IA é utilizada na sociedade. Ex: Uma tecnologia para visão computacional foi usada em máquinas de guerra, sad example :(.

**IA pode criar erros ocultos** como Chatbots com posturas preconceituosas, veículos autônomos que podem sacrificar vidas...

**IA pode levar à perda de habilidade e pensamento crítico**, ou seja, motoristas perdendo as habilidades nas ruas, o senso de decisão das pessoas diminui com os algoritmos de recomendação...

**IAs podem ser manipuladas**, podem ser invadidas. Ex: Algoritmos de recomendação podem privilegiar alguns produtos ou pessoas...

**IAs podem institucionalizar viéses**, ou seja, algoritmos que aprendem com uma base de dados, estão limitados à esses dados e tomam características desses dados. Ex: algoritmo recomenda só currículos de homens para vagas de engenharia...

**IAs podem causar perda de empatia**, ou seja, serviços podem se tornar muito automatizados e com pouca interação pessoal (chatbots).

**IAs podem causar perda de controle**. Eles tomam decisões, é preto no branco, ou seja, o sentimento humano, os dilemas humanos não entram nessa equação. Uma IA deixaria de tirar uma vida inocente, sendo que essa tarefa foi dada à ela?

**IAs podem ter implicações sociais muito além do seu negócio**, ou seja, ela pode aprender para se tornar mais inteligente e fazer além do que foi diretamente programada.

**Empregados ainda precisam ter seus papeis**, ou seja, a IA não pode tomar totalmente o lugar do trabalhador. Ela pode causar perda de empregos, mas pode criar novos empregos.

**A tecnologia deve honrar os direitos fundamentais, a segurança e privacidade pessoal**.

---

---

---

# Unity 2

### Data Science - What is?

**O profissional de Data Science:** *Extrasão de conhecimento a partir dos dados!*

- **Conhecimento de Computação:**  
  que irá permitir ao profissional manipular corretamente os dados, criar programas que automatizem o processamento desses dados, utilizar algoritmos para extrair conhecimentos dos dados e criar modelos e soluções a partir do conhecimento extraído desses dados.
- **Conhecimento de Estatística:**  
  que irá permitir ao profissional explorar e compreender os dados e construir modelos a partir desses dados.
- **Conhecimento do Domínio:**  
  que permitirá ao profissional entender o problema a ser atacado e compreender o significado dos dados.

*É aplicado em TUDO, na área da saúde, das finanças, E-commerce, CRM...*

**Processo da Ciência de Dados:**

1. Fazer uma pergunta interessante - Definição do problema (O que quero com os dados?). Tal pergunta deve ser bem formulada, deve ser uma pergunta orientada à dados, ou seja, utilizando dados eu posso resolver tal problema, tal pergunta;
   
   - Transformar o problema, ou desejo de negócio em uma pergunta orientada à dados -> É necessário uma análise de fatos e julgamentos com base no negócio da empresa e pensando também nos dados disponíveis.
     
     - Fatos: Coleta os dados "óbvios" para aquela análise, dados diretamente relacionados;
     
     - Julgamentos: Precisa pensar em fatores relacionados de forma indireta. Suposições que podem influênciar no cenário e agregar na análise.
     
     - Exemplo: Devolução de Produtos -> Fatos: Defeito na envoltura, fora da validade, produto estragado, fora de especificação... Julgamentos: Quem fabrica a envoltura? Quem comercializa? Como o produto foi estocado? Como é transportado? e por ai vai. 

2. Coletar os dados - Fase que pode enriquecer os dados também, com terceiros;

3. Explorar os dados - Fazer uma limpeza nos dados, ver o que ta faltando...

4. Modelar os dados - Contruir modelos (estátisticos, redes neurais...) são os modelos que vão tentar extrair conhecimento dos dados, responder nossas perguntas iniciais...

5. Comunicar e visualizar os resultados - Com dashboards, qualquer interface ou modo de aprensentar os resultados.

**Tipos de dados:** 
