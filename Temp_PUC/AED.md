---
title: Algoritmos e Estrutura de Dados (Puc-Minas - 2º Período)
author: Arthur P. Braga
---

### Notes

**1ª e 2ª Aula ->** Como vai ser a aula e formação de grupos de trabalho;

**3ª Aula ->** Tipo abstrato de dados (TAD - mesma coisa de classe abstrata);

**4ª Aula ->** Continuação da explicação de TAD || Java Extension Pack (VSCode)

---

**5ª e 6ª Aula ->** Recursividade

- Descubra a **repetição**, depois a **regra de formação** e depois o **ponto de parada**.

Exemplo de uma multiplicação usando recursividade:

```java
public static void main(String[] args) {
  System.out.println("A multi = "+mult(2, 3));
}

public static int mult(int n1, int n2){
  if (n1 == 0) return 0;
  else return n2+mult((n1-1), n2);
}
```

---

**7ª Aula ->** Busca binária (pesquisa sequencial) e debate te atividades

---

**8ª Aula ->** Introdução a análise de complexidade de algoritmos

- Regras precisas;

- Cobrir todos os pontos de parada;

- Consumir o menor nº de recurso no menor tempo possível;

*Técnica de força bruta pra preencher um sudoku poderia levar 750.000.000 anos*

Para saber o custo de um algoritmo você pode executar um programa e medir o tempo.

**Passos:** Para que serve o algoritmo -> Qual a operação mais importante -> Quanto tempo se gasta? (equação) IMPORTANTE!!!!!

Existem três cenários: 

- Pior caso -> f(n) = n

- Melhor caso -> f(n) = 1

- Caso Médio -> f(n) = (n+1)/2.

Todos se relacionando com a quantidade de trabalho que foi necessário para alcançar o objetivo; 

---

**9ª Aula ->** Exemplos de análise de complexidade de algoritmos

<img title="" src="file:///home/arthurbraga/Documentos/Programming_Study/imgs/Analise_Algoritmo.png" alt="">

f(n) = 2*(n-1) ou f(n) = 2n - 2 

---

**10ª Aula ->** Continuação análise de algoritmos

- **Comportamento assintótico**:  É o comportamento das funções de custo para valores grandes de n. Assintota.

- **Ordem de complexidade - O(n)**. Uma função vai ser da ordem de complexidade da outra quando ela tem o mesmo comportamento que essa outra. Essa ordem de complexidade é aproximadamente o limite em que tal algoritmo é "viável".

**Classes de complexidade**

- Complexidade **fixa ou constante** (melhor caso possível, porém limitado): Uma complexidade constante executa um nº fixo de vezes independente do tamanho de n (da quant de dados). Ex: Um array ordenado que pega o maior elemento. Ex2: Fazer uma troca de dois nº de posição em um array;

- Complexidade **logarítmica**: Resolve problemas transformando-os em problemas menores. Se o algoritmo resolve divindo o problema a cada passo. Ex: Busca binária;

- Complexidade **Linear**: Um trabalho é realizado sobre cada elemento de entrada. Ex: Procurar um elemento em um array desordenado;

- Algoritmos **n*log n**: Quebram o problema em partes menores, mas resolve cada um deles independentes e depois agrupam as soluções (dividir para conquistar);

- Algoritmos **quadráticos**: O(n²) itens processados aos pares. Para problemas relativamente pequenos.  Ex: Um loop dentro do outro.

- Algoritmos **cúbicos**: O(n³) Sempre que n dobra, o tempo é multiplicado por 8. Ex: 3 loops, um dentro do outro. Multiplicação de matrizes;

- Algoritmos **exponenciais**: O(2^n) Não são úteis sob o ponto de vista prático. Sempre que n dobra, o tempo é elevado ao quadrado. Ex: Força bruta;

- Complexidade **Fatorial**: O(n!) Comportamento muito pior do que O(2^n). Ou seja, em vez de 2x2x2x2... vai ser 2x3x4x6.... Ex: Para o nº 40 em um algoritmo desse, executado no PC mais poderoso do mundo demoraria SÉCULOS; 

---

**11ª Aula ->** Estrutura de dados

**Memória principal ->** "imenso array" de bytes.

Declaração de variável é uma abstração dos endereços de memória.

Cada variável tem seu nome, endereço e valor;

**Ponteiros ->** É uma variável que armazena um endereço de memória. Usado com Strings, por exemplo. Ou seja, como o tamanho da String depende, e pode variar muito, ele só faz uma referência para a área da memória que caiba a String.

*Tipos básicos: valores copiados - Objetos: referência*

**Alocação dinâmica de memória:** Ele reserva um espaço para um ponteiro, para futuramente poder fazer uma referência. 

---

**12ª Aula ->** Estruturas de dados -> **Filas**

*Dados "ordenados" por chegada - first in first out (FIFO)*

Exemplos em sistemas:

- Atendimento Bancário;

- Pedidos de reservas na biblioteca;

- Processamento de alteração de matrículas;

- Venda de ingressos.

**Fila estática:** Tem um tamanho fixo, podendo ou não estar totalmente ocupado. Um vetor pode ser usado para representar uma fila simples, mas não é uma fila, pois não tem regra (qualquer um pode sair a qualquer hora....).

Para isso precisa de um vetor e duas variáveis (capacidade do vetor e quantidade contida ele).

*Os valores sempre vão entrar atrás da posição do ultimo valor (que será a variável qtd).*

Valor de escape: valor que nunca terá seu lugar na fila.

---

**13ª Aula ->** Continuação de Filas

**Filas Dinâmicas (ou encadeadas):** Seus elementos são inseridos e retirados ao longo da execução do programa - dinamicamente. Não tem uma previsão da memória total necessária e nem previsão da quatidade de alterações necessárias quando se retira um valor.

- O elemento da fila inclui uma referência para o próximo elemento (ponteiro). Logo pode-se criar um novo elemento e apontar para outro.

- *Potencialmente infinito*

---

**14ª Aula ->** Listas encadeadas

*Interligação de elementos - Pode ter um ordenamento ou não.*

- Não há uma regra de inserção e retirada;

- Difícil de prever a demanda de memória total necessária.

Ex: Lista de trabalhos - Controle de processos em um SO...

*A estrutura da fila e da lista é a mesma, o que muda é a regra!*

**Métodos de lista:** Inserir - Deletar - Localizar - Concatenar listas

- **Localizar:** 
  
  1. A partir do início, avançar i posições na lista.
  
  2. Localizar pelo valor.

- **Retirar da posição i:** Primeiro a gente precisa localizar. 

**Listas duplamente encadeadas:**

*Passa a ter duas referencias por elemento. - Dois apontadores, um para o próximo elemente, e outro para o anterior.*

---

**15ª Aula ->** Pilhas

*Estrutura empilhada, ou seja, coloca e retira dados somente por cima.*

*LIFO (last in, first out)*

**Usos**:

- Analogia clássica: pilha de pratos (Não faz diferença se você pegar o 1º dado, ou o último, ou qualquer outro);

- Chamadas de funções;

- Crtl+Z;

- Debug;

- Inversões (pois o ultimo q entra é o primeiro que sai).

*Pode criar um contador para limitar o uso de memória.*

**Notação polonesa reversa (pós-fixa):** modo como escreve as operações para o computador interpretar corretamente (a operação vem depois dos números).

Para usar a notação polonesa precisa de duas pilhas, uma para criar a equação polonesa e outra para resolver.

---

**16ª Aula ->** Árvores

Todas as estruturas anteriores eram *lineares* (seguir em linha reta vai passar por todos os dados) - As arvores são estruturas não-lineares, existem **caminhos** à se seguir, **com hierarquia**.

Exemplos: Estrutura de diretório do Unix S2; Git S2

*nodos (nós) ou vértices = elementos de uma árvore*

**Grau de um nodo:** Quantidade de descendentes diretos que ele tem. Elementos de grau 0 = folha;

**Nível de um nodo:** Distância do nodo até a raiz.

**Altura de um nodo:** Distância do nodo a folha mais distânte (pior caso de complexidade).

**Subárvore:** Conjunto de elementos com uma raiz comum.

É uma estrutura recursiva, pois uma arvore é uma raiz e suas subárvores, e uma subárvore é uma árvore.

**Árvore binária de busca:** Cada nodo só tem até dois filhos e os valores à esquerda são sempre menores que os valores à direita.

---

**17ª Aula ->** Continuação de árvores || Atividade avaliativa

**18ª Aula ->** Código de árvore

---

**19ª Aula ->** Continuação de código de árvore  || Árvores Balanceadas AVL

**Árvores Balanceadas AVL:** Busca rápida, mas só em uma estrutura bem balanceada, bem comportada (mal comportada ele aproxima de O(n), uma busca sequencial).

*Uma árvore balanceada tenta manter as alturas das duas dubávores equilibradas.*

Uma árvore balanceado precisa ser criada já balanciando, não da pra balancear depois de preenchida.

---

**20ª Aula ->** Filas de prioridades

**Heap (amontoado - pirâmide - árvore binária completa):** Para criar uma fila que tenha alguma prioridade (o primeiro a sair é o menor elemento, por exemplo), se faz uma heap, onde o mais prioritário é a raiz. O nº de operações necessárias para se organizar uma heap é  muito menor (O(log2 de n)) que uma estrutura de fila simples (O(n)).

*Existe uma correspondência entre uma árvore binária e um vetor.* Sendo x uma posição, os filhos estão a uma distância x dele.

---

**21ª Aula ->** Mapas, dicionários e skiplists

**Mapas:** Vai mapear! kkk traça caminhos para localizar.

- Estrutura de amazenamento *associativo*.
- Usa identificador para seus valores: Par key-value(object) (k,v) é conhecido como entrada de dados. Todas as operações são baseadas na key;
- Vantagem: é possivel de indexar os mesmos dados por atributos diferentes, utilizando múltiplos mapas (id sendo o nome, ou matricula...);

Dicionários: É a msm coisa do mapa, porém dicionário pode ter chave duplicada.

- Exemplo: Agrupamento de objetos. Atributos multivalorados (um livro pode ter varios autores).

Se a estrutura não precisa ser ordenada:
*Podemos implementar com uma lista duplamente encadeada e/ou Arrays*
Se precisa ser ordenado:
*Pode usar Arrays ordenados (gasta operações para ordenar msm), mas possibilita a busca binária.
Da pra usar lista duplament encadeada tbm, mas não possiblitará a busca binária.*

Skip Lists: Estrutura de dados composta que permite implementar estruturas de dicionário com mais eficiencia nas operações.
- Se utiliza o fator aleatório para obter bons desempenhos nas operações;
- Por ser composta ela usa 2 ou + estruturas para produzir uma;
- É uma lista de listas. A 1ª lista do conjunto tem todos os dados ordenados. E o resto das listas contém um subconjunto aleatório dos dados
Cada lista precisa ter dois sentinelas (valores -infinito e +infinito)
Para cada item de uma lista, temos o sentinela de uma outra lista LDE (lista duplamente encadeada);

---

**22ª Aula ->** Continuação de Skip lists || Tabela Hash
 Skip List depende do aleatório!

- A quantidade de listas é log2 n;
- Gasta mais memória, mas a velocidade de busca é maior;

**Tabela hash(picadinho):** Ela não vai comparar ninguém, ou seja, não tem busca sequencial, nem árvore binária... tbm chamado de tabelas de dispersão. Transformação aritmética da chave de pesquisa. Usa função com o id do dado, o resultado é o endereço do dado na tabela (tabela imagem). Ou seja, endereçamento direto, vai direto no endereço que ele quer.
- O problema é que ela é bijetora, ou seja, para cada elemento de um, só tem um correspondente, só um resultado. Logo não tem como ter id duplicado ou que seus resultados vão ser iguais;
- Os metodos de inserção e busca é a mesma;
- Colisão: duas chaves vão para a mesma posição. Precisa trata-las.

**Paradoxo do aniversário:** Cenário onde a gente acha q a probabilidade do resultado da conta ser igual é muito pequena, mas na vdd é bem grande. 

**Funções hash comuns:** 
- f(x)=x, o problema é o uso de espaços ociosos. Ex: quando usa nº de matrícula, cpf...
- f(x) = x % N (N=tamanho da tabela), o problema é que de o valor de entrada for par o resto vai ser par, e a mesma coisa para valores ímpares, e isso prejudica a probabilidade. Além do perído de dar restos iguais. Recomenda-se escolher para N um nº primo. Se o dado não for numérico -> Transformação (unicode), mas precisa prestar atenção em casos de anagrama, nesse caso utiliza peso para os caracteres, suas posições...
- Extrair dígitos da key.
- Quebrar a key. Ex: elevar a key ao quadrado, e depois, extrair dígitos. 

**Tratamento de colisões:**

- Lista encadeada: cria uma lista de listas, ou seja, para cada posição vc insere o dado em uma lista endereçada com aquela posição.
- Utilização de lugares vazios na própria tabela: Tendo lugares vazios na tabela, quando ocorre um conflito o dado é armazenado no lugar vazio. *Usado quando tem-se uma boa estimativa inicial da quantidade de registros a ser armazenada.* Métodos para busca de posição vazia:
  - Sondagem linear: procurar a próxima posição livre - vai somando 1 para ir verificando as próximas posições. Nesse caso para fazer a busca do elemento desejado, caso o resultado da função não dê a posição do elemento desejado, a gente precisa fazer uma busca sequencial até achar. *Em case de busca por elemento inesistente é feita a busca sequencial até achar uma posição vazia.*;
  - Sondagem quadrática: Em vez de procurar linearmente, a posição a ser sondada, é determinada pelo quadrado da tentativa. Ex: h j(x) = (h(x) + j^2) % N || j = tentativa;
    - Duplo hash (double hashing): Para aumentar ainda mais a dispersão das tentativas de busca por posições vazias a gente escolhe uma 2ª função hash -> h(x,i) = (h(x) + i*h(x)) % N || i = tentativa;

**Remoção de elemento em tabela hash:** No caso de endereçamento aberto não pode excluir o çelemento "de verdade", pois pode dar ferrar com a busca de um elemento. Logo o elemento precisa ter um atributo "boolean valido;" = marca de remoção, logo na busca ele não vai existir se a marca for false, e não vai ser considerado null na busca e por isso nao ferra o processo. 

*A tabela hash tem uma tendencia à ficar "bagunçada" ao longo do tempo, logo é recomendável fazer a reorganização da tabela de tempos em tempos. Para isso você cria uma nova tabela e percorre a antiga verificando um a um e vendo se está válido, se está na posição adequada...*

*Tabela hash não serve muito para dados ordenados!*

---

**23ª Aula ->** Continuação de tabela hash

**24ª Aula ->** Continuação de tabela hash

---

**25ª Aula - Lab ->** Ordenação: Métodos básicos

Ordenação estável (ex: dois numeros iguais, se um estiver atrás, sempre tem q ficar atrás), posicional, por comparação.

**Por comparação:** 

Custos: nº de comparações, complexidade...

- **BubbleSort:** Vai jogando os maiores valores para o final do vetor. Comparando a posição relativa do elemeto atual com o próximo elemento. Toda vez que encontra uma posição relativa correta, tu volta pro inicio e faz com outro elemento. **O(n)** para vetor ja ordenado, e **O(n²)** para ter que ordenar.
- **SelectSort:** Pega a ordem de grandeza de cada elemento e coloca na posição adequada. Menor elemento -> coloca na posição 0 -> 2º menor elemento -> coloca na posição 1.... **O(n²)**, porém poucas trocas, "pouco recurso computacional". Esse método não é estável.
- **InsertSort:** Olha para todas as posições anteriores, se for menor tu troca. **O(n²)**. Esse método é estável.
- **ShellSort:** Antes de ordenar por inserção (um por um) ele faz uma ordenação parcial para deixar o vetor mais longe do pior caso possível. Vai ficar mais ordenado para a ordenação por inserção. *Em vez de olhar posição por posição, ele compara de 3 em 3 posições para trás, por exemplo. Logo a ideia, na verdade, é ordenar subsequencias, pedaços do vetor (ordenação parcial).* A ordem de complexidade depende, é menor do que O(n²), mas o quão menor não tem como saber. **Método não estável**.
  - Diminuição progressiva do valor do gap (pulo - intervalo de comparação) até que chegue em 1. Ex: Roda o vetor com gap=4, depois roda com gap=2, depois gap=1.
  - Para um gap eficiente -> h = 3*h + 1
  - Tamanho moderado do vetor. Se o vetor for muito pequeno, pode implementar os métodos anteriores, se for MUITO grande, ai esse método para de compensar. Precisa ser no meio termo para compensar.
- **MergeSort:** Recursivamente ele divide o vetor, até ficar pequeno o bastante, ordena os subvetores rapidamente, e depois intercala para o vetor final. Para intercalar no final, como é recursivo, ele volta o caminho contrário da divisão. O problema é: se o vetor for muito grande, vai ter muita recursividade, logo MUITA memória necessária para ser utilizado. E pior, para a intercalação, precisamos criar um vetor aux. Intercalação = **O(n)** e Recursividade = **O(log n)**  OU SEJA O(n*log₂n). **Método estável.** 
- **HeapSort:** Utiliza Heap, logo o primeiro que sai (o 1º da lista) é o que tem maior prioridade. Se já tem uma heap no sistema, vale a pena usar. **Complexidade = Construir: O(n) || Refazer: O(log n) -> O(n log n). Método não estável.** (Filhos de uma posição -> 2i+1)
- **QuickSort:** Define um pivô e separa o vetor, os menores para um lado do pivô, e os maiores para o outro lado do pivô. Ex de pivô: último elemento do conjunto. Uma vez feita a divisão, nunca mais vai comparar os elementos da esquerda com os da direita. Depois, de forma recursiva, faz o mesmo processo para os lados, até q sobre só o próximo pivô e um elemento. **Particionamento: O(n) || Recursividade: O(log n) -> O(n log n).** Problema: Má escolha do pivô pode levar o algoritmo a O(n²). Pode não se comportar bem em vetores "quase ordenados". Pior caso: vetor já ordenado. **Método não estável.**
  - Recomendação de Cormem: escolher 3 posições aleatórias e escolher como pivô a mediana destas posições.

**Ordenação posicional:**

Determina as posições parciais ou finais dos dados realizando um pré-processamento.

- **Ordenação por contagem:** Bom para quando sabemos que tem repetição de valor. Faz a contagem da quant de cada valor... Ai a soma do valor com a quantidade é a posição inicial desse valor no vetor final. **Complexidade ->** **O(n)** (2*n para ser exato ou até 4n) || **Espaço ->** Ocupa memória por ter que criar um vetor aux e a tabela de contagem, e se os dados não se reperitem vc ainda terá 3 vetores do mesmo tamanho || **Estabilidade ->** True;
- **RadixSort ou ordenação digital:** Raiz - parte principal - ex: INFORmação INFORmatica... 
  - **LSD ->** Mini hash para cada nº da chave, ordenando uma casa decimal por vez (direita para a esquerda). 2 problemas, cada posição tem uma lista de elementos (pode necessitar de espaço) e dependendo da key, para pegar o decimal individualmente pode aumentar a complexidade. Outro problema é que essa ordenação é boa para nº mas para ordem alfabetica nem tanto. **Complexidade ->** O(n);
  - **MSD ->** Esquerda para a direita, ou seja, pega o maior (most) valor primeiro. Exemplo dado na aula foi para ordem alfabetica. Utiliza recursividade, para cada posição que tem uma lista com mais de um elemento (empates), ele cria outro vetor e faz o mesmo processo para a prox letra dos nomes. Pode usar memória PARA UM CARALHO (depende de quantos empates vai ter). **Complexidade ->** O(n) (n * a pior quantidade de empates).

---

**26ª e 27ª Aula ->** Continuação de ordenação

**28ª Aula ->** Explicação do trabalho || Revisão de estrutura de ordenação || Dúvidas

**29ª Aula ->** Ordenação posicional

DROZDEK, Adam. Estrutura de dados e algoritmos em C++

TP - PROVA - Exercicio avaliativo (2 questões - 1ª teorica qual algoritmo.. - 2ª passo a passo de um algoritmo)