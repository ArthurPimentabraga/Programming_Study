---
title: Programação Orientada por Objetos (Puc-Minas - 3º Período)
author: Arthur P. Braga
---

## Notes

---

## Aula 1 - 04/02

#### Apresentação da disciplina

#### Revisão de conceitos

- **Valor**: Dado atribuido a uma posição na memória para ser operado/usado. Valor é usado no programa. Valor representa um dado contido em uma posição na memória.
- **Variável**: Nome dado à representação do valor. "Ponteiro para o valor".
- **Tipo da variável**: Indica como a variável vai ser usada. Também indica quanto espaço vai usar na mamória.
- **Vetores e matrizes**: Para alocar mais de uma variável, criar um conjunto de variáveis, do mesmo tipo e relacionadas.
- **Métodos**: Conjunto de instruções com uma finalidade.

---

## Aula 2 - 05/02

#### Criação de um sisteminha do jogo de dados (Par ou Ímpar)

*Só pra ter uma ideia de POO.* 

---

## Aula 3 - 11/02

#### Fundamentos de POO

*Orientação por objetos abstrai o mundo real utilizando objetos que interagem entre si.*

**Análise orientada para objetos** (OOA/AOO): Examina os requisitos de um sistema de uma perspectiva de classes e objetos, usando o vocabulário do domínio do problema.

**Projeto orientado por objetos** (OOD/DOO): Projeto no qual o processo da decomposibilidade em objetos é utilizado e modelos físicos e lógicos de objetos são descritos.

**Programação orientada por objetos** (OOP/POO): Implementar o planejamento.

- POO, segundo *Alan Kay:*
  - Troca de mensagens
  - Proteção e retenção local e ocultamento do estado (dados) ou processo
  - Associação tardia e dinâmica de tudo o que for possível

**Procedural x POO**

- Procedural: Instruções executadas em um fluxo que visa o desempenho de uma tarefa específica.
- POO: Conjunto de objetos que interagem entre si, porém preserva sua individualidade e tem um papel específico na execução de uma tarefa.

#### Análise e projeto OO

**Tipo abstrato de dados** (TDA): reúne na mesma estrutura, informações sobre dados, e comportamento de uma entidade representada a partir do mundo real.

**Classe**: Descrição padronizada de um tipo abstrato de dados. Modela um conjunto de entidades do mundo real que possuem características e comportamentos semelhantes.  É o esquema/representação/modelo de uma "entidade genéria".Constituída por atributos e métodos. Ex: Classe caneta, classe carro... 

**Objeto:** É a instância de uma classe, é um "exemplar" daquela classe. Ex: Classe usuário - Objeto João.

---

## Aula 4 - 12/02

#### Exercício de modelação de classe

**UML**: Linguagem de modelagem universal.

---

## Aula 5 - 18/02

#### Modularidade

É a divisão do sistema em partes distintas. Um módulo é um **grupo de comandos** com uma **função/propósito** bem definida e o mais **idependente** possível em relação ao resto do algoritmo. *Unidade identificável na compilação.*

Consequentemente mais seguro, pois divide o sistema e permite modificar um lugar sem alterar o outro. Facilitando o desenvolvimento e reúso da solução;

##### Coesão

As classes precisam ser coesas, não pode ter pontas soltas (precisa ter ligação com o sistema, e de forma lógica/inteligente). Um sistema com alta coesão:

- Facilita e acelera a manutenção;
- Reduz efeitos colaterais e propagação de erros;
- Dependência deve ser intra-modular: uso e dependência resumidas ao máximo nas estruturas internas ao módulo.

##### Abstração 

Uma classe deve incluir somente os atributos de importância em um contexto particular. Precisa ter os atributos (dados) necessários para a utilização daquela entidade no sistema. 

- Conceito da caixa-preta: Entrada e saída bem conhecidas, mas com detalhes ocultos.
- A ideia principal é não ser necessário saber os detalhes do funcionamento de um objeto para utilizá-lo.

#### Encapsulamento

**Proteger!** É o princípio da ocultação de informação e do conceito de caixa preta. Seguir regras (validações) para manter os dados...

- Proteger os dados do acesso direto a partir de um código externo (oculta). Garantindo que as regras sejam seguidas, permitindo o acesso e uso deles somente da forma correta/definida.
- Os atributos de uma classe só deveriam ser acessador e modificados por meio de seus métodos, deixando os atributos sempre 'private'. Geralmente usando getters e setters (métodos de acesso) para retornar e setar os valores. Isso impede alterações indevidas, por exemplo.

---

## Aula 6 - 19/02

#### Getters and Setters

#### Atividade prática

---

## Aula 7 - 25-02

#### Revisão/Discussão da atividade proposta

#### Construtor

Método especial responsável pela implementação de ações necessárias para criar um objeto. Instruções pré-definidas para que uma classe sempre seja criada de maneira válida.