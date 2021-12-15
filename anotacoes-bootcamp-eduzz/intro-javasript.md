# Notas sobre Javascript

 - Livescript mudou para Javascript.
 - Criada por Brendan Eich.
 - Linguagem interpretada.
 - Linguagem de tipagem fraca (não há verificação em todos os tipos no script).
 - Linguagem dinâmica (não precisa explicitar o tipo da variável no momento da execução).
 - Função de primeira classe e ordem maior significa que a função pode ser atribuida a uma variável, a uma estrutura de dados, passadas por argumentos e até retornadas por outras funções.
 - Javascript suporta programação estruturada e orientada a objetos.

### Comentários

 - Linhas de código ignoradas que servem de informações para quem escreve o código.
 - Tipos de comentários:
  - // ... : comentário de uma linha.
  - /* ... */ : comentário de múltiplas linhas.

### Tipos de dados

 - todo tipo de informação que possui um significado para o computador, por exemplo.
 - Tipos de dados: 
	- **undefined**: tipo de dado que pode ter sido declarado, mas não foi definido.
	- **null**: nada.
	- **boolean**: tipo que aceita valores verdadeiro ou falso.
	- **string**: variável do tipo texto.
	- **symbol**: tipo primitivo de variável que é imutável.
	- **object**: tipo de variável que pode conter vários tipos de variáveis.
	- **number**: é um número.

### Variáveis

 - Nomes de variáveis e funções são case sensitive.
 - Camel Case: é quando a variável tem dois nomes e o segundo nome é iniciado por maiúscula (e.: "camelCase).
 - Boa prática: atribuir nomes em caixa alta para constantes (Ex.: const PRECO). 
 - Tipos de variáveis:
	- **var**: varável que tem escopo global, ou seja, pode ser "vista" pelo programa em qualquer parte do código.
	- **let**: só pode ser acessada no escopo onde foi declarada.
	- **const**: variável que não deve, ou não pode ser mudada ao longo do programa.
 - Declarar e atribuir:
	- var a: apenas declara a variável "a".
	- var a = 7: declara e atribui um valor à variável.
 - Declarar variável do tipo string
	- utiliza-se aspas simples ou aspas duplas.
		Ex.) var nome = "Fulano";
		Ex.) var resposta = ""; (declara uma string vazia) 

### Closure 

 - É o algo como "escopo léxico", que é a capacidade de uma função lembrar do ambiente em que ela foi criada.

 - Escopos do Javascript:
  - Escopo global.
  - Escopo de função.
  - Escopo de bloco (let e const).

#### Escopo de variáveis
 - Global:
	- Variável que é definida fora de um bloco de função.
	- A variável fica visível por todo o programa. 
	
    '''
            var globo = 10;
            function funciona() {
	            var saida = "";
	            if (typeof globo != "undefined") {
		            output += "variavel global: " + globo;
            	}
            }
    '''
    
    '''
            var globo = 10;
            function funciona1 () {
	            carambola = 5;    // declarar sem var dentro da função torna a variavel global
            }			         // declarar com var dentro da função torna a variável           local
            function funciona2() {
	            var saida = "";
	            if (typeof globo != "undefined") {
	            	saida += "variavel global: " + globo;
	            }
        	    if (typeof carambola != "undefined") {   // se tiver sido declarada com var, será undefined.
		            saida += "carambola: " + carambola;
	            }
            }
'''

 - Função:
	- Variáveis que são declarada dentro de uma função tem escopo local.
	-  Só são visíveis dentro da função em que foram declaradas.
'''
            function escopoLocal() {
	                var numero = 5;
	                console.log(numero);
            }
            escopoLocal();
            5
            console.log(numero);
            undefined
'''
 - Bloco:
	- Sofrem hoisting.		

### Caracteres de escape de strings

 - Usa-se um "\" antes das aspas para prevenir erros na interpretação da string.
	Ex.) var citacao = "A frase \"ser ou não ser, eis a questão\" é de Shakespeare".

### Concatenar strings

 - Para concatenar strings, usa-se o sinal de "+".
 - É preciso deixar um espaço antes do fechamento das aspas
	Ex.) var frase = "Um prato " + "de sopa";
	Ex.) var frase = "vem fácil, " ---- > frase += "vai fácil" ---> frase = "vem fácil, vai fácil".
	Ex.) var nome = "fulano"; var sauda = "Olá, " + nome; "Olá, fulano";

### Tamanho da string

- Método ".length" retorna o tamanho da string informada.
'''
        var tamanhoString = 0;
        var nome = "Fulano";
        tamanhoString = nome.length;
        console.log(tamanhoString); ----> 6
'''

### Arrays
 - Para declarar um array, usa-se colchetes ("square brackets") e vírgulas para separar os elementos.
 - Um array multidimencional, nested array, é um array que possui arrays internos.
	Ex.) var pessoa = ["Fulano", 32];		
	Ex.) var classe = [["Fulano", 14], ["Beltrana", 13]]; 
 - Para acessar um array:
'''
        var meuArray = [30,25,47,27];
        var resp = meuArray[1];
        console.log(resp); ----> 25
'''
 - Modificar um array:
'''
        var numeros = [10,20,30];
        numeros[1] = 69;
        console.log(numeros); ---> 10,69,30
'''
 - Acessar array multidimensional
'''
        var numeros = [[7,4,1], [5,9,3], [6,7,2]];
        var escolhe = numeros[1][2];
        console.log(escolhe) ----> 3
'''
### Métodos com arrays

#### ".push()": 
 - adiciona itens no fim do array.
'''
        var meuArray = ["Fulano", "Beltrano"];
        meuArray.push(["Ciclano", "Ninguem"];
        console.log(meuArray); ---> [Fulano, Beltrano, Ciclano, Ninguem];
'''
#### ".pop()"
 - remove o último elemento de um array.
'''
        var meuArray = ["Fulano", 31], ["Beltrano",35];
        var novoArray = meuArray.pop();
        console.log(novoArray); ---> [Fulano, 31] 
'''
#### ".shift()"
 - remove o primeiro elemento de um array.
'''
        var meuArray = ["Fulano", 31], ["Beltrano",35];
        var novoArray = meuArray.shift();
        console.log(novoArray); ---> [Beltrano, 35] 
'''
#### ".unshift()"
 - adiciona um elemento na primeira posição de um array.
'''
        var meuArray = ["Fulano", 31], ["Beltrano",35];
        var meuArray.unshift("Ciclano", 32);
        console.log(meuArray); ---> [Ciclano, 32] 
'''

### Matemática básica

 - Adição:
	- Para adicionar números, basta usar o sinal de "+".
		Ex.) var soma = 10 + 10.
 - Subtração:
	- Para subtraior, basta usar o sinal de "-".
		Ex.) var sub = 15 - 9.
 - Multiplicação:
	- Para multiplicar, usar o sinal "*".
		Ex.) var mult = 13 * 7
 - Divisão:
	- Para dividir, usar o sinal "/" (barra ou slash)
		Ex.) var quociente = 18 / 9
 - Incremento
	- Incrementar significa adicionar um valor a variável.
		Ex.) var a = 89 ---> a = a + 1 = 90 ---> a++ = 90
 - Decremento
 	- Decrementar significa diminuir um valor da variavel.
		Ex.) var a = 90 ---> a = a - 1 = 89 ---> a-- = 89
 - Resto da divisão
	- Resto ou "remainder".
	- É o resto de uma divisão é assinalado por um sinal de "%".
	- Frequetemente usado para saber se um número é ímpar ou par.
		Ex.) remainder = 11 % 3.

### Funções

#### Declaração de função:

 - Funções permitem a reutilização de códigos dentro do programa.
 - Dentro das chaves fica o código que será executado quando a função for chamada.
'''
        function nome_funcao() {
        	console.log("Hello, World");
        }
        nome_funcao();
        Hello, World
'''

#### Parâmetros da função:

 - Parâmetros são variáveis que agem como marcadores de posição de valores que serão passados a uma função.
'''
        function subtrair(a,b) {
        	console.log(a-b);
        }
        subtrair(10,6);
        4;
'''

### ECMAScript

 - Especificação padronizada pela European Computer Manufactorer Association (ECMA).
 - ECMAScript é apenas uma especificação de como a linguagem deve ser implementada, não está ligada diretamente aos navegaadores.
 - TC39 é o comitê responsável evolução do Javascript, mantém e atualiza os padrões ECMAScript.
 - Fluxo de proposta no TC39:
   - Stage 0 - strawman
   - Stage 1 - proposal
   - Stage 2 - draft
   - Stage 3 - candidate
   - Stage 4 - finished
 - ES2018:
  - Operadores rest/spread
  - Iteração assíncrona
  - Promise.prototype.finally()
 - ES.Next

### Typescript
 - Adiciona tipos e funcionalidades que o js não tem por padrão (interface, genéricos...).

### Currying 
 - Transforma uma função com n parâmetros em um função que recebe apenas um parâmetro. 
 - Curried function é um conceito da programação funcional na qual uma função recebe multiplos parametros um de cada vez. 
 - Você invoca a função com menos parâmetros do que ela é capaz de receber e essa invocação vai retornar outra função.
 - A vantagem de usar currying é a possibilidade de escrever códigos flexíveis e reutilizáveis.
'''
        const getDesconto = desconto => preco => preco * desconto;
        const getDezPorcento = getDesconto(0.10);
        console.log(getDezPorcento(747)
        74.7
'''

### Hoisting
 - Um dos motivos para haver o escopo de bloco com let e const.
 - Em inglês, significa "levantar algo", içar.
 - As declarações de variaveis e funçõess são elevadas no escopo em que elas estão.
 - Hoisting de variavel só eleva a criação/declaração da variável e não sua atribuição/inicialização.
 - Hoisting de função é elevada como um todo. 

### Imutabilidade
 - Os dados que são criados não mudam ao longo do código.

### Design Patterns
 - Soluções reutilizáveis para problemas comuns do projeto.













