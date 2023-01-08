# Teórica 12

## *Refactoring*

- Forma disciplinada de limpar o código e minimizar as chances de introduzir *bugs*;
- Quando se faz *refactor*, está-se a melhorar o *design* do código após este ter sido escrito;
- Irá provocar alterações no sistema de *software* de uma forma que não alterará o comportamento exterior do código, melhorando a sua estrutura interna;
- Quando se faz *refactor* podemos ter um *design* muito mau, até mesmo caótico, trabalhando-o de forma a torná-lo em código bem desenhado;
- É uma série de pequenos passos, cada um com alterações à estrutura inicial do programa sem alterar o comportamento externo.

### Porquê?

- Melhora o *design* do *software*;
- Torna o *software* mais fácil de entender;
- Ajuda a encontrar *bugs*;
- Ajuda a programar mais rápido.

### Razões para fazer *refactoring*:

- Código duplicado;
- Rotina demasiado longa;
- *Loop* demasiado longo ou demasiado *nested*;
- Classe com pouca coesão;
- Interface de classe que não providencia um nível consistente de abstração;
- Lista de parâmetros tem demasiados parâmetros;
- Alterações dentro de uma classe tendem a ser compartimentalizadas;
- Trocas requerem modificações paralelas a múltiplas classes;
- Hierarquias de herança devem ser modificadas em paralelo;
- *Case statements* devem ser modificados em paralelo;
- Iténs de dados relacionados que são utilizados em conjunto não se encontram organizados em classes;
- Uma rotina utiliza mais atributos de outra classe do que da sua própria classe;
- Um tipo de primitiva de dados está demasiado sobrecarregado;
- Uma classe não faz muito;
- Uma cadeia de rotinas passa *tramp data*;
- O objeto *middleman* não está a fazer nada;
- Uma classe está demasiado relacionada com outra;
- Uma rotina tem um mau nome;
- Membros dos dados são públicos;
- Uma subclasse apenas utiliza uma pequena percentagem das rotinas dos seus "pais";
- Comentários são utilizados para explicar código difícil;
- Variáveis globais são utilizadas;
- Uma rotina utiliza um código de *setup* antes de chamar uma rotina ou um código de término após chamar uma rotina;
- Um programa contém código que parece que será preciso um dia.

### Dicas 

- Quando percebermos que temos de adicionar uma funcionalidade a um programa e o código do programa não está convenientemente estruturado para essa adição, primeiramente devemos fazer o *refactor* para ser fácil adicionar a funcionalidade e apenas após isso adicioná-la;
- Antes de iniciar o processo de *refactoring*, devemos verificar se temos uma base sólida para testes *self-checking*;
- Se tivermos um fragmento de código que pode ser agrupado, devemos tornar o fragmento num método que tem um nome que explique o seu propósito;
- Devemos trocar o programa em passos pequenos para facilitar o processo de descoberta de possíveis falhas;
- 

#### Trocar o nome de variáveis

- Bom código deve comunicar claramente aquilo que está a fazer;
- Nomes de variáveis são chave para limpar o código;
- Devemos mudar os nomes para melhorar a percetibilidade das coisas;
- Com boas ferramentas de *find-and-replace* é fácil de fazer este processo;
- Ter um *strong typing* e *testing* vai realçar as falhas;
- Qualquer um pode escrever código que o computador perceba, mas apenas os bons programadores escrevem código que os humanos percebem.

#### Mover um método

- Um método está a utilizar ou é utilizado por diversas funcionalidades de outra classe e não da qual na que está definido:
  - Deve ser criado um novo método com um corpo semelhante na classe que o utiliza mais;
  - Em seguida, torna-se o método antigo para uma simples delegação ou remove-se.

#### Trocar *temp* por *query*

- Devemos livrar-nos de variáveis temporárias redundantes, pois estas podem causar que múltiplos parâmetros desnecessários sejam passados de um lado para o outro;
- Facilmente, perde-se o fio desses parâmetros e o porquê de estarem onde estão;
- Isto pode causar uma quebra de desempenho, visto pedirmos a execução de mais *queries*.

#### Método *inline*

- O seu corpo é tão claro como o seu nome;
- Colocar o corpo do método no corpo das funções que o chamam e remover o método.

#### Introdução de uma variável explicativa

- Existe uma expressão complicada;
- Colocar o resultado da expressão (ou partes dela) numa variável temporária com um nome explicativo.

#### Substituir um algoritmo

- Um algoritmo pode ser substituído por um mais claro;
- Trocar o corpo do método pelo novo algoritmo.

#### Extraír uma Classe

- Uma classe faz o trabalho de duas classes;
- Cria-se uma nova classe e move-se os campos/métodos relevantes para a nova classe.

### *Refactoring* e *Design*

- *Refactoring* é um complemento ao *design*;
- Pode ser uma alternatica ao *upfront design*:
  - O programador programa e depois efetua o *refactor* para o formato pretendido;
  - Engenheiros de *software* fazem o *design upfront*, mas não tentam encontrar a solução, embora precisem de uma solução razoável.
- *Refactoring* podem levar a *designs* simples sem sacrificar a flexibilidade;
- Assim, torna-se o processo de *design* mais fácil e menos stressante. 

### *Bad Code Smells*

- *Bloaters* são unidades de código que aumentaram em tantas proporções que se tornaram difíceis de trabalhar com;
- Geralmente, estes *smells* acumulam-se ao longo do tempo enquanto o programa evolui;
- *Object-orientation abusers smelss* são aplicações incorretas ou incompletas dos princípios da programação OO;
- *Change preventers smells*: se temos de trocar algo num sítio do código, temos de fazer múltiplas operações noutros sítios, também;
- Desenvolvimento de *software* torna-se muito mais difícil e caro;
- Um *dispensable* é algo insignificante e inútil que a sua inexistência tornaria o código mais limpo, mais eficiente e mais fácil de entender;
  - Por exemplo, *dead code*.
- *Coupler smells* contribuem para o *coupling* excessivo entre classes.

## Mensagens Chave

- *Refactoring* é uma série de pequenos passos, em que cada um irá alterar a estrutura interna do programa sem alterar o seu comportamento externo;
- Antes de se iniciar o processo de *refactoring*, devemos verificar que temos uma boa base para *self-checking tests*;
- *Refactoring* troca o programa em **passos pequenos**.