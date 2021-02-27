---
title: CSS
author: Arthur P. Braga
---

### Some Selectors

- **Pseudo-Classe ->** O seletor indica estados ou situações de elementos HTML. 
  
  ​    Ex: p:First-of-typy{} or p:actived{} or p:hover{} ...;
  ​            .class:nth-child(9) -> pega o 9º elemento daquela classe;​    

- **Pseudo-Elemento ->** Seletor que indica PARTES do elemento HTML para serem manipuladas.
  
          Ex: p::first-letter{} (modifica a 1º letra de cada parágrafo) or p::after{} ...;

- **Universal ->** Modifica todos os elementos css da pág.
  
          Ex: *{margin:0} (todos os elementos ficam com margin 0);

#### Combinações de Seletores

**p, ul{} ->** todos os p e ul receberão tais manipulações;

**li.active{} ->** todos os elementos li que tiverem a class .active receberão tais manipulações;

**div p{} ->** todos os elementos p que são descendentes de uma div receberão tais manipulações;

**div>p{} ->** todos os elementos p que são filhos de uma div receberão tais manipulações, ou seja, o p precisa ser a primeira tag dentro de div;

**li.active + li{} ->** o próximo elemento li depois do li que contém a class active receberá tais manipulações;

**li.active ~ li{} ->** os próximos elementos li depois do li que contém a class active receberá tais 
        manipulações;

#### Prioridades de Seletores

A prioridade é dada pela ordem de leitura, a especificidade e pela caracteristica !important;

- Na ordem prevalece a última;

- Na especificidade, de maior para menor: comando inline - id - class - elemento HTML
  
  - Para calcular a especificidade pode dar +1 ponto para cada surgimento deles.
    
        Ex: #wrapper li{} -> especificidade de 0,1,0,1 <- este é prioridade 
               li.active{} -> especificidade de 0,0,1,1

- Se colocado o !important no modificador css, ele se torna prioridade;

------------------------------------------------------------------------------------------------------

### Position and Display

------------------------------------------------------------------------------------------------------

### Transform and Keyframes

------------------------------------------------------------------------------------------------------

### Layout Responsivo

- **Tipos de Layout:**
  
  - **Líquido ->** É contruído quase que inteiramente por %. O layout somente se ajusta à tela em que está sendo exibido;
  - **Fixo ->** Tal layout é contruído para uma tela específica, ou seja, para uma quantidade específica de pixels. E se for exibido em uma tela com uma quantidade inferior de px pode resultar nas famosas barras de rolagem horizontal, conteúdo muito pequeno...;
  - **Responsivo ->** Contruído por % e px; Basicamente é um layout líquido, porém há inteligência, ou seja, alguns elementos podem se redimencionar dependendo do tamanho da tela, podem mudar de posição... todo necessário para melhor experiência em qualquer tela. (É a mais cara e demorada. Imagina se esconde um anúncio...);

- **Mobile First:** Uma boa técnica é começar a construir o site para o mobile e depois adaptar para o desktop. (O acesso de site pelos smartphones é predominante). Com isso cria-se vantagens, como: Vantagem no ranqueamento do google com a prioridade da versão mobile; Sem gambiarras para adaptar para mobile; Site pensado mais para o mobile, então um melhor ux...; 

- **Projeto:** 
  
  - **1º Mapa Conceitual ->** Criar uma teia interligando todo conteúdo à ser exibido no site;
  - **2º Mapa do site ->** Com o mapa conceitual, cria-se o mapa do site o qual organizará o conteúdo à ser exibido, irá criar uma arquitetura de navegação;
  - **3º Wireframe ->** É um desenho da tela em que se deseja exibir o site, com elementos representativos, ou seja, organiza o conteúdo na tela, decidindo como será exibido, como se comportará...
  - **4º Taskflow ->** Mostra a sequência de ações possíveis de serem feitas no site, por exemplo, os passos para o cadastro;

------------------------------------------------------------------------------------------------------

### Viewport and Media Queries

- **Viewport ->** É a área visível para o usuário de uma página web. Se não for definida a forma como ela se comportará, em casos em que a tela tem uma quantidade de px diferente, como quando é visualizado no celular, a viewport tenta colocar todo conteúdo dentro dela, deixando assim textos muito pequenos...  

- **Definição ->** <meta name="viewport" content="X,Y,Z">
  
          - X-> Largura da viewport, definida com pixels fixos ou device-width que pega o tamanho max;
          - Y-> Define a escala inicial, ou seja, um usuário pode, já por definição do seu dispositivo, ter uma escala(zoom) maior ou menor, então definindo como 1, a viewport volta para a escala em que foi produzida;
          - Z-> Define os limites da escala(zoom) que o usuário pode dar. Não é usado pq o mesmo pode ter algum problema visual e querer dar muito zoom, por exemplo; 

```html
<meta name="viewport" content="width=device-width", initial-scale=1">
```

- Breakpoints: São os pontos de mudança de layout usado em MediaQueries. Em outras palavras é o tamanho de tela(hardware) que informamos à tag media para quando um dispositivo estiver naquela resolução, usar o css adequado. Porém em dispositivos menores, o tamanho da resolução da tela(resolução lógica) não é a mesma que do hardware (os Breakpoints usam a resolução lógica).
  - Já existem Breakpoints prontos na web, mas tem como calcular. Basta dividir a resolução física (hardware) pela razão de pixel do dispositivo(encontrado na especificação do mesmo). As viewport == a resolução lógica == aos Breakpoints;

------------------------------------------------------------------------------------------------------

### FlexBox and Grid

- **FlexBox:** Indicado para criar layout que se comportem em uma única dimenção, seja linha ou coluna. Quando se deseja juntar linhas e colunas é utilizado o grid. Com o layout flex não precisa se preocupar com quantidade de itens, quebras de linhas... Já faz isso tudo automaticamente.

- Códigos padrões para o flexbox: 
  
  - **display:flex; ->** "ativa" o modo flex;
  - **flex-wrap: wrap; ->** Quebra de linha (mas também existem tipos para esconder o item...);
  - **justify-content: space-between; ->** cria espaçamentos entre os itens;
  - **align-items: center; ->** alinha os itens no centro;

- **Grid:** A diferença do grid para o flex é que ele é multidimensional. Ou seja, podemos fazer com que 1 item ocupe o lugar de dois em uma coluna ou linha, como se mesclasse as células do excel;

- Códigos padrões para o grid:
  
  - **display: grid; ->** "ativa" o modo grid;
  - **grid-template-columns: repeat(3, 1fr); ->** quantidade e tamanho de colunas em um grid. Neste caso será um grid com 3col, e todas do mesmo tamanho. Também pode ser escrito assim: (1fr 2fr 1fr), o que significa que serão 3 colunas porém a 2º ocupará o lugar de 2;
  - **max-width: XXXpx; ->** define o tamanho da largura do grid;
  - **grid-gap: XXpx; ->** define o espaçamento entre itens;
  - **grid-column and grid-row ->** especifica em qual linha e coluna (de qual linha até qual linha ele vai também) um item em específico vai ficar; 

------------------------------------------------------------------------------------------------------

### Menu for Mobile

- O menu responsivo pode ser feito basicamente com um checkbox, com labels(em icons) controlando ele. O css irá, por meio de uma MediaQuery, dar "show e hide"(display block and none) para mostrar e esconder as labels. E verificando se o CheckBox está ativo ou não, o css mostrará ou esconderá o menu vertical.

------------------------------------------------------------------------------------------------------

### Unidades de Medida

1in = 96px = 2,54cm = 25,4mm = 72pt = 6pc

- **vw**: 1% da largura da viewport;

- **vh**: 1% da altura da viewport;

- **vmin**: a menor medida entre vw e vh;

- **vmax**: a maior medida entre vw e vh.

- **cm - centímetro**;

- **mm - milímetro**;

- **q - 1/4 do milímetro**;

- **in - polegada** ;

- **pc - pica**;

- **pt - point**;

- **px - pixel**;