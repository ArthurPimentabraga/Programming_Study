---
title: Introdução à Sistemas Inteligentes (Puc-Minas - 2º Período)
author: Arthur P. Braga
---

## Unity 1

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

- **Dynamic Scripting ->** O sistema cria uma séria de "regras" (scripts) e testa os mesmos com o jogador, se determinado script teve uma resposta positiva, ele o usa mais vezes. Ex: Em um jogo de luta se o script de *atacar e recuar* quando o jogador está no meio da tela funcionar, ele usa esse script mais vezes (esse script ganhou pontos);

- **Previsão ->** O sistema pode estudar seus padrões de jogabilidade para, por exemplo, saber aonde você irá chutar no fifa.

##### Música

Possibilidades:

Descobrir quais musicas você pode gostar de ouvir || Reconhecimento de musica || Composição de musica (Uma IA já criou o final de uma sinfonia inacabada) || Você canta a musica e o app reconhece a musica || Até ajustar o timbre da voz do cantor para ficar afinado

##### Saúde
