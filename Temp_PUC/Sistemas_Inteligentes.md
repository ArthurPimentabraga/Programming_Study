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

- **Agente reativo simples ->** seleciona ações com base na percepção atual, ignorando o restante do histórico de percepções.
  
  Ex: aspirador de pó.
  
  **Características**
  
  - Utiliza regras de condição ação (pré definidas)  
    ***if* *X* *then* *Y***
  - Depende apenas da percepção atual.

- **Baseado em modelos ->** possui um estado interno, que dependa do histórico de percepções (modelo do mundo em que atua). Ou seja, com esse modelo ele pode ter dados probabilísticos que ajudam a tomar melhores decisões. 
  
  **Características**
  
  - Possui um modelo de como o mundo funciona evolui sem o agente.
  - Possui um modelo de como as suas ações podem afetar o mundo.
  - Mistura a percepção atual com o modelo antes de agir.
  - Pode utilizar histórico de percepções para "compreender" como o mundo evolui.
  
  *Um agente baseado em modelos pode ajustar gradativamente o modelo que ele tem do mundo na medida em que vai explorando o ambiente.*

- Baseado em objetivo -> É definido um objetivo para o agente e ele tomará decisões, escolherá suas ações para alcançar tal objetivo.
  
  **Características**
  
  - Possui um modelo de como o mundo funciona evolui sem o agente.
  - Possui um modelo de como as suas ações podem afetar o mundo
  - Utiliza objetivos, ao invés de regras de condição-ação, para escolher uma ação ***que o leve na direção de seu objetivo***.
  - Um objetivo então poderá ser definido como sendo um estado do ambiente que se deseja alcançar.

- **Baseado em utilidade ->** *Medida de performace das ações do agente*. 
  
  **Características**
  
  - Utiliza uma medida de desempenho (utilidade) ao invés de objetivos que permitem apenas uma distinção binária.
  - Ao contrário do objetivo, uma medida de utilidade não precisa estar relacionado com um estado final do ambiente, mas com uma ***medida de desempenho do agente***.
  - Exemplos incluem: um carro autônomo pode definir como medida de performance o tempo, a distância, ou medidas mais abstratas como menor consumo de combustível. Dessa forma, o carro autônomo irá escolher a ação que irá maximizar a medida de utilidade desejada.

- **Sistema multiagente ->** agentes comuns mas que podem se comunicar. Dessa forma os agentes podem se coordenar para atingir um objetivo em comum com maior eficiência, por exemplo.

- **Agente com Aprendizagem ->** pode ser dividido em quatro componentes: 
  
  - **Elemento de Aprendizado**: responsável pelo aperfeiçoamento do elemento de desempenho.
  
  - **Elemento de Desempenho**: qualquer um dos outros tipos de agente completo que se deseja ajustar.
  
  - **Crítico**: indica para o elemento de aprendizado se o agente está obtendo sucesso, baseado em um padrão de desempenho.
  
  - **Gerador de Problemas**: sugerir ações que levaram a experiências novas e informativas (explorar novas possibilidades).

*Pode combinar os tipos de agentes no seu sistema*

---

### IA na Sociedade

##### Democratização da IA

APIs :)

**Na sociedade ->** Como a IA é utilizada na sociedade. Ex: Uma tecnologia para visão computacional foi usada em máquinas de guerra, *sad example :(*.

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

5. Comunicar e visualizar os resultados - Com dashboards, qualquer interface ou modo de apresentar os resultados.

---

### Análise Exploratória e Preparação de dados

##### Tipos de dados:

**Dados Quantitativos:** Numéricos

- **Normalizados:** Variam dentro de um limite, ou seja, vão variar somente dentro daquele limite. Muito usado com taxas [0...1].

- **Não normalizados:** Podem variar, não podemos garantir que estarão dentro de um limite. Ex: Idade, peso, altura...

- **Escala intervalar:** São aqueles dados que não podem ter uma razão entre eles. Ex: Graus Celsius e Fahrenhit (não da para tirar razão entre eles, pois não tem um zero absoluto, ou uma relação direta das temperaturas. Só se converter um para outro). *Esse tipo só pode ser "não normalizado".*

- **Escala racional:** Dados que podem ter uma razão entre eles. Possuem um zero absoluto, um significado absoluto. Ex: nº de consultas em um hospital. *Esse tipo pode ser normalizado.* 

**Dados Qualitativos:** Não Numéricos

- **Dados Binominais/Binários:** Dois valores. Ex: Sintoma de febre: sim/não.
  
  - **Binominais simétricos:** Ambos os valores possuem a mesma relevância. Ex: Masculino/Feminino (Se não é um, é outro).
  
  - **Binominais assimétricos:** Apenas o valor positivo é relevante. Ex: Assistiu um filme (Se ele assistiu tal filme, saber disso é importante, para uma recomendação por exemplo. Mas se ele não assistiu não quer dizer que não gostou, simplesmente ninguém consegue assistir todos os filmes do mundo ou de uma base de dados).
    
    - Dica: Dados esparsos. Ex: Termos de um documento (tu não vai levar em conta todas as palavras do dicionário, e sim quais apareceram no documento). Ex2: Sintomas de doenças, ou seja, existem centenas de sintomas, mas só será relevante as que o paciente teve.

- **Dados Polinomiais/Categóricos não ordinais:** Uma ou mais palavras que não são ordenadas naturalmente. Ex: Setor: Limpeza, laticínios, cosméticos... 

- **Dados Categóricos ordinais:** Palavras que são ordenadas naturalmente. Ex: Faixa etária: criança, jovem, adulto, idoso.

##### Estatística descritiva

*Técnicas para descrever e sumarizar um conjunto de dados. Ou seja, organizar os dados.*

**Medidas e propriedades:**

- **Frequência:** Nº de vezes que o dado acontece no conjunto.
  
  - Frequência absoluta: Quantas vezes ele aparece. 
  
  - Frequência relativa: É a frequência em relação ao todo. Ex: em um conjunto de 18 números, o 11 apareceu 3 vezes. Então sua frequência relativa = 3/18 = 0.17 = 17%.

- **Média:** Para mexermos com média é necessário cuidado, precisamos retirar o maior e o menor valor do conjunto, pois se forem muito discrepantes, vão alterar o nosso resultado.

- **Mediana:** Se o conjunto for par -> média dos dois elementos do meio.

- **Moda:** Valor mais frequênte.

- **Percentil:** São medidas que dividem o conjunto de dados em 100 partes (conjunto ordenado). Cada parte com uma porcentagem aproximadamente igual. 
  
  - Ex: Conjunto -> {1,2,3,4,4,5,6,6,7,8} || 5º percentil = 4.

- **Quartil:** [O que é Quartil (Medidas Separatrizes) #74 - YouTube](https://youtu.be/qlBk00ismYE)

**Medidas de Espalhamento:**

- **Intervalo** = valor máx - valor min;

- **Variância:** O quanto aquilo está variando em relação à média. Mais longe e mais perto da média. 

<img title="" src="file:///home/arthurbraga/Documentos/Programming_Study/imgs/variancia.png" alt="" width="355"> X = média

- **Desvio padrão:** O quão confiável é aquela variância. Ou seja, o quanto os valores que foram utilizados para calcular aquela variância vão se diferenciar.  Cálculo => raíz quadrada da variância.

- **Desvio médio absoluto:** subtrai cada elemento pela média, soma esses módulos e depois divide por n;

- **Desvio mediano absoluto:** pega a mediana de todos os módulos (dado - média);

- **Intervalo interquertil:** quartil75% - quartil25%;

##### Processo ETL (Extract-Transform-Load)

*Business Intelligence -> Conjunto de conceitos e metodologias que, fazendo uso de dados e acontecimentos (fatos), apoia a tomada de decisões em um negócio. Tais técnicas basicamente são focadas em extrair informações úteis de múltiplas e volumosas fontes de dados brutos e Sistematizados.*

*KDD - Knowledge Discovery in Databases*

**Processo ETL:**

- Extrair: Buscar os dados. Externos e/ou Operacionais. (TXT, Banco de Dados, Redes Sociais, Excel....) Também é feita a limpeza desses dados; 

- Transformar: Sumarizar, Aprimorar, organizar os dados... (padronizar nomenclatura, cálculos necessários...);

- Carregar: Carregar em um repositório de destino, organizar esses dados em algum lugar. Pode fazer um pré-processamento para confirmar que está tudo correto. Tipicamente o processo é feito em lotes.

##### Machine Learning

*É o estudo de algoritmos que melhora a medida da experiência - O sistema aprende através de dados reais.*

Tomam suas proprias decisoes, decidem se suas ações foram boas, e se "auto melhoram".

<img title="" src="file:///home/arthurbraga/Documentos/Programming_Study/imgs/MachineLearning.png" alt="">

**Estilos de aprendizado:**

- Supervisionado -> São dados que já contém as "respostas", uma base de dados rotulada, ou seja, ele pega os dados já com os padrões... e começa a definir regras em cima deles. Muito usado para previsão, recomendação...

- Não supervisionado -> Identifica os padrões nos dados. Ex: Agrupamento de semelhantes, segmentar grupos de clientes...

- Semisupervisionado -> Combina os dois anteriores. Metade rotulada, e a outra metade ele rotula de forma não supervisionada com o que aprendeu anteriormente.

- Por reforço -> Não são definidas nenhuma regra, somente uma medida de desempenho, um objetivo. Ex: muito usado em games.

- Deep Learning (Aprendizado profundo) -> Quando os dados não tem características muito bem definidas, é usado redes neurais, deep learning. É um algoritmo com várias camadas, muito bem estruturado e mais complexo que consiguirá extrair características mais definidas dos dados. *Um modelo mais complexo para objetivo mais complexo.*

**Principais tarefas de  Machine Learning**

- Descritivas: Analisar dados passados para entender como aquilo funciona.
  
  - Agrupamento (Clustering): Segmente automaticamente a base de dados em grupos por suas similaridades e diferenças. Ex: Campanhas de marketing direcionadas, email padrão direcionado para determinados clientes... *K-means*
  
  - Associação: Encontrar padrões frequentes, associações... *Quem compra A compra B em 60% das vezes*. Ex: Comércio eletrônico com recomendação de produtos, super mercados... *Apriori*

- Preditivas: 
  
  - Classificação: Faz a classificação das classes de elementos dos nossos dados. Ou seja, ele extraí as características de cada elemento, e faz a análise. Ex: Identificar qual o objeto em uma foto. *Árvore de decisões*
  
  - Regressão: Técnicas estatísticas para estimar a relação entre variáveis ou atributos para prever valores futuros. (lembrar de função - é usado para calcular os possíveis valores). *Redes neurais*

**Árvore de decisão**

Tomada de decisão - Classificação
