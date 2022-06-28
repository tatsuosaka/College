# Tipos de dados expressões, operações e tabela verdade

Compreender os conceitos dos tipos de dados suportados pela linguagem e suas manipulações para o desenvolvimento de aplicações robustas e eficientes.

***

## **Módulo 1 - Empregar os conceitos de tipos de dados por meio de manipulação de variáveis e constantes na linguagem C**

Um algoritimo pode ser entendido como uma linha de produção.

Exemplo:

- Para o cálculo do índice de massa corpórea (IMC) de uma pessoa, medimos sua altura e seu peso.

A representação em casas decimais de números tão comuns do nosso dia a dia também pode ser feita nas linguagens de programção.

Para desenvolver um algoritimo precisamos:

1. Identificar quais dados de entrada serão utilizados e como representálos em nossa linguagem de programação.
2. Fazer a transformação necessária para modificar ou realizar cálculos.

Desde sua concepção, a linguagem C possui quatro tipos de dados básicos: **char, int, float e double**. Por meio deles e de suas manipulações é possível representar qualquer tipo de informação.

- **Char**: Representa um caractere(letra, número ou símbolo) e ocupa um byte na memória, representado pela tabela **ASCII** com seus 256 símbolos.

- Os 32 iniciais são símbolos de controle
- Do 32 ao 127 compõem a tabela ASCII
- Do 128 ao 255 pertencem à tabela ASCII estendida

**Manipulação de variáveis e constantes**

1. **Conceito**: A **variável** é um tpo d eespaço de memória que pode ser alterado a qualquer tempo.

A **constante** por sua vez, não pode.

As duas formas permitem a referenciação deles em um espaço de memória que são identificados por meios de rótulos. Chamados de identificadores, eles possibilitam a partir de seu uso o acesso ao conteúdo armazenado em memória.

2. **Definição das variáveis**: Para criar uma variável, utiliza-se a seguinte notação:

`tipo nome_do_identificador;`

Podemos definir as variáveis com outro formato:

`tipo nome_do_identificador_1, nome_do_identificador_2;`

Não é recomendavel definir uma quantidade muito grande de variáveis de uma só vez, pois isso dificulta o entendimento do código-fonte.

**Uma variável sempre deve ser definida antes de seu uso.**

***

## **Módulo 2 - Aplicar os operadores matemáticos, lógicos, relacionais e de atribuição, além dos conceitos de tabela verdade**

1. **Operadores matemáticos**

- a) **Operacionalidade**: Soma, subtração, multiplicação ou divisão são operações que funcionam exatamente da mesma forma que no mundo real

- b) **Classificação**:

- *Unários*: Chamados de incremento ou decremento.
- *Binários*: Têm dois operandos.
- *Ternários*: Três operandos.

2. **Operadores relacionais**

- Menor `<`
- Maior `>`
- Menor ou igual `<=`
- Maior ou igual `>=`
- Igualdade `==`
- Diferente `!=`


3. **Operadores lógicos**

- *Unários*: Operador de negação `!`, retorna o oposto dela.
- *Binários*: e-lógico `&&`, ou-lógico `||`.

4. **Operadores bit a bit**

- 1 byte: O tipo caractere ocupa um byte na memória.
- 4 bytes: O tipo float ocupa quatro bytes na memória.

5. **Operadores de atribuição**

Usado para armazenar valores na memória, por exemplo:

o IMC representado na linguagem C

`IMC = peso / (altura*altura);`

Armazenado na variável IMC

6. **Operadores de conversão**

Este tipo de operador permite uma "tradução" entre valores diferentes. Com ele é possivel converter valores de tipos de dados diferentes. Pode ocorrer de duas formas:

- **Sem perda de informação**: Converte um tipo que ocupa uma quantidade menor de memória para outro com uma quantidade maior.
- **Com perda de informação**: Converte um tipo de dado de maior tamanho ocupado em memória para outro com um tamanho menor.

Exemplo:

- Considere a variável pi com valor 3,1415, se quisermos converter este número para uma variavel inteira o resultado seria igual a 3. Portanto perdendo o decimal 0,1415

**Tabela verdade**

|    **a**   	|    **b**   	|  **a&&b**  	|
|:----------:	|:----------:	|:----------:	|
| verdadeiro 	| verdadeiro 	| verdadeiro 	|
| verdadeiro 	|    falso   	|    falso   	|
|    falso   	| verdadeiro 	|    falso   	|
|    falso   	|    falso   	|    falso   	|

|    **a**   	|    **b**   	| **a\|\|b** 	|
|:----------:	|:----------:	|:----------:	|
| verdadeiro 	| verdadeiro 	| verdadeiro 	|
| verdadeiro 	|    falso   	| verdadeiro 	|
|    falso   	| verdadeiro 	| verdadeiro 	|
|    falso   	|    falso   	|    falso   	|

|    **a**   	|    **b**   	|  **a->b**  	|
|:----------:	|:----------:	|:----------:	|
| verdadeiro 	| verdadeiro 	| verdadeiro 	|
| verdadeiro 	|    falso   	|    falso   	|
|    falso   	| verdadeiro 	| verdadeiro 	|
|    falso   	|    falso   	| verdadeiro 	|

|    **a**   	|    **b**   	|   **a^b**  	|
|:----------:	|:----------:	|:----------:	|
| verdadeiro 	| verdadeiro 	|    falso   	|
| verdadeiro 	|    falso   	| verdadeiro 	|
|    falso   	| verdadeiro 	| verdadeiro 	|
|    falso   	|    falso   	|    falso   	|

|    **a**   	|   **~a**   	|
|:----------:	|:----------:	|
| verdadeiro 	|    falso   	|
|    falso   	| verdadeiro 	|