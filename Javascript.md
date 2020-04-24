---
title: Javascript
author: Arthur P. Braga
---

### What is

- É responsável pela interação do site com o usuário;
- É interpretado no navegador;
- ECMAScript é uma padronização de linguagem de scripts, ou seja, JavaScript, JScript e ActionScript seguem a ECMAScript, porém cada um tem suas particularidades;
- Uma linguagem de scrips não é usada para construir uma aplicação por completo, e sim para dar interatividade, de elementos já existentes, com o usuário;

----------------------------------------------------------------------------------------------------------------------------

### Commands and codes:

- confirm -> exibe uma caixa igual o alert, porém pedindo confirmação;
- prompt -> Mesma caixa, porém com um textbox para ser preenchido;
- typeof (var ou valor) -> Descobrir o tipo da variável (terminal node);

```Javascript
Number.parseInt(var) -> Converção de variável, podendo ser para int, float...;
Number(var) -> Converte para número, o js que decide qual tipo, float ou int;
String(var) ou var.ToString() -> Converter para string;
.toFixed(nº) -> nº de casas decimais;
.replace('','') -> troca algo por algo. Ex: . por , em um double; 
.toLocaleString('pt-BR', {style: 'currency', currency: 'BRL'}) -> formata por uma string 
    localizada, ou seja, formata um int qualquer em uma "moeda". Ex: 1500 -> RS1,500,00;

var**var -> Operador que eleva o 1º nº pelo 2º;

.sort() -> ordena os valores de um array;
.pop() -> remove o último valor do array, e também o retorna;
.push(value) -> acrescenta uma posição final no array e insere o valor nele;
.shift() -> remove o primeiro valor do array, também retornando-o;
.unshift(value) -> acrescenta uma posição no início do array e insere o valor nele;

.forEach(item) -> passa por cada item de um vetor; 

JSON.stringify() -> converte um objeto em String;
JSON.parse() -> converte a String de um obj em um obj novamente;
```

*Função de forma reduzida↓*

```javascript
id.evento = (parm) => bloco de comandos;
```

----------------------------------------------------------------------------------------------------------------------------

### Meanings

- **Infinity and -Infinity ->** pega o maior e o menor nº possível de se guardar em uma variável;

- **NaN ->** "Not a Number", ou seja, se tentar fazer uma operação com uma letra, por exemplo, retornará NaN; 

- " " e ' '-> Qualquer uma, porém se for juntar html com js, sempre usar uma para cada. Precisa ter essa diferença; 

- Acento grave -> 

  > 1ºuso: usa para placeholder ${} (placeholder é para incluir var dentro de um string por ex);
  >
  > 2ºuso: quando queros dar quebra de linha para uma string, com `` o "Enter" funciona;

- === -> Operador de igualdade restrita, ou seja, ele verifica se os dois valores são idênticos,
      em valor e no tipo da variável. Diferente do == que so verifica o valor;

----------------------------------------------------------------------------------------------------------------------------

### Notes

- O sinal de + pode concatenar e somar, depende do tipo da variável. O prompt sempre retorna string;
- Operadores relacionais como ">" também funcionam em letras, as letras só representam os bytes em nosso pc, logo uma letra tem uma posição, um "valor", então "a" é > que "b", "a" é > "A", "Dezena" é > que "Dez" por ter mais caracteres...
- Pode usar 'For in' para loops com arrays, é mais simplificado;

----------------------------------------------------------------------------------------------------------------------------

### Document Object Model

- DOM é um conjunto de objetos do navegador que nos permite ter acesso aos componentes internos do nosso site, sejam eles: tags HTML, a localização atual no meu site(em que página o usuário está no momento), o histórico de navegaçãono site...

  

- O acesso à tais componentes é feito de diversas forma, só é necessário respeitar a hierarquia da árvore DOM(os componentem tem uma hierarquia, ou seja, a raiz é "windows", tem vários filhos como "location", "history", "Document"... Document por sua vez tem seu filho "HTML", que por sua vez tem seus filhos "HEAD" e "BODY", que tem seus filhos que são as tag html....);

  

- Em "Document" o acesso pode ser feito por nome das tags, id, class, querySelectors...

  - Ex: windows.document.QuerySelector('div#menu'); Ele vai selecionar a div que contém o id == menu;
  - Ex: windows.document.getElementsById('menu'); Ele vai selecionar o elemento que contém o id == menu;
  - Ex: windows.location.href; Captura a URL atual;

  

- Eventos DOM é tudo o que pode acontecer com um elemento específico. 

  - Ex: quando o mouse passar em cima desse elemento(click, mouseenter, mouseout, mousemove)...

```    javascript
.addEventListener('event', function); -> Cria o evento para determinado elemento sem ter que setar no HTML; 
```

---

### Form

- Eventos podem ser inseridos no form para diversas finalidades, como o evento input (oninput) que seria chamado a cada mínima alteraçao no campo. Um exemplo prático é fazer com que se o usuário digitar um caracter inválido para aquele campo, o mesmo é excluido ou aparece uma mensagem de erro. Outros eventos: focus, blur, change....

---

### Others

- Uma boa técnica é armazenar um dado localmente no navegador do usuário, desta forma pode se criar "interações" que facilitam a vida do mesmo, como deixar armazenado seu login para que todas vez que for logar no site já estar preenchido para ele.

  - Existem duas formas de armazenamento local 

  ```javascript
  localStorage.getItem('chave'), setItem('chave',valor), removeItem('chave') ou clear() 
  	(recuperar, armazenar, remover e limpar todos os dados, respectivamente);
  sessionStorage.// // // //
  ```
  - A diferença é que localStorage salva por tempo indeterminado, já o session salva somente naquela sessão;