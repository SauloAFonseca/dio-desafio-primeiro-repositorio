# Notas sobre Typescript

### Informações Gerais
 - Adiciona checagem de tipos
 - Não é uma linguagem, é uma extensão da linguagem javascript.
 - Menos erros em tempo de execução
 - Facilidade de manutenção
 - Adiciona tipos estáticos ao código
 - Pode ser usado com react, vue, angular e node
 - Usa extensão .ts e .tsx
 - Typescript Compiler (TSC) compila arquivos .ts para javascript
 - Arquivo tsconfig.json é usado para configurar com o Typescript opera.
 - Typescript transpila o código em ES3
 - Parcel é um Node Package Manager (npm) para transformar, compilar e reunir assets(complementos de um website como folhas de estilo, imagens, scripts...)
 - Um bundler, por sua vez, permite que a aplicação funcione no navegador. Ele analisa o código e gera um novo arquivo com as partes necessárias para que funcione.

### TSC
 - Typescript compiler
 - É responsável por compilar, checar e observar mudanças nos códigos.
 - Converte o código Typescript para código Javascript 
 - comando para compilar o arquivo em um arquivo javascript.
```
tsc index.ts
```

### Prós e Contras
 - **Prós**:
    - mais robustez
    - fácil localização de bus
    - previsibilidade
    - legibilidade
    - popularidade
 - **Contras**:
    - requer compilação
    - não usa tipos estáticos verdadeiros

### INTERFACES
 - Usadas do mesmo modo que as structs em linguagem C.
 - São criadas com a palavra-chave **interface** e possuem a estrutura de um objeto (propriedades e métodos).
 - Agrupam conjuntos de dados e estabelecem uma relação entre eles dentro de uma variável.
 - const input = document.getElementById("input") as HTMLInputElement.
 - Typescript entende os objetos automaticamente(by default).
 - Métodos em interfaces:
    - **extends**
	- **implements**
 - **Extends** indica que a classe criada **herda** propriedades e métodos da "interface pai" e pode, ou não, adicionar novas características.
 - **Implements** indica que a classe ou objeto criado deve possuir **também** as propriedades/métodos da interface indicada.
 - Por padrão, as propriedades definidas dentro de uma interface são obrigatórias. Contudo, é possível definir propriedades e métodos opcionais. 
 - O sinal de interrogação na definicão de uma variável informa ao Typescript que aquela propriedade ou método é opcional. 
```
	interface User {
		name: string:
		age?: number;
		greetings(): string;
	}
	const user: User = {
  		name: "Fulano",
		age: 30,
		greetings() {
			return "Hello, " + nome
	}
 	};
	const user2: User = {
		name: "Beltrano",
		greetings() {
			return "Hello, " + nome
  	};
```

### tsconfig
 - possibilita a configuração do typescript e a definição de parâmetros.
 - o arquivo tsconfig.json pode ser gerado com o comando tsc --init

### rootDir
 - local onde serão armazenados os arquivos
 - "./src"
 - typescript transpila os arquivos presentes em "src" para o diretório "dist"

### outDir
 - ajuda a definir um local específico onde ficarão armazenados os arquivos javascript
 - "./dist"

### Variáveis
 - as definições de variáveis são as mesmas de javascript: var, const e let.
 - após criar uma variável, o seu valor só pode ser mudado para um valor do mesmo tipo: string-string, number-number... (type inference)
 
### Função

 - Utiliza os mesmos modos de criação que o ES6.
 - Em Typescript, a função getFullName = (name, surname) pode ter seus parâmetros definidos de acordo com o tipo de variável que se espera receber.
```
	const getFullName = (name:string, surname:string) => {.....}
```
 - É boa prática em Typescrip explicitar tudo, bem como o tipo de retorno. Veja o exemplo do definição do tipo de dado do retorno.
```
	cons getFullName = (nome:string, surname: string): **string** => {
		return name+" " + surname
```
	
### Generic Types
 - Cria um tipo de código que pode ser reutilizado por não estar ligado a um tipo específico de dado.
 - É indicada pelos sinais de <.....>
```
const algumaCoisa = <T>(objcto:T)=> {
	let id = Math.random()
}
```

### Access Modifiers
 - o acesso aos dados pelo programa é orientado pelo pilar do **encapsulamento**.
 - modificadores de acesso (access modifiers) controlam a visibilidade dos dados.
 - 3 tipos de access modifiers em Typescript:
	- public
	- private
	- readonly
	
#### public
 - É o modo de acesso padrão aos dados
 - pode ser acessado fora da classe de declaração
 - pode ser declarado ou omitido, dado que é o modo padrão de acesso. 

```
class Employee {
    public empCode: string;
    empName: string;
}
```

#### readonly
 - a palavra-chave "readonly" transforma o acesso a um atributo em apenas leitura. 
 - o atributo readonly pode ser acessado fora da classe de declaração, mas seu valor não pode ser modificado fora dela. 
 - a definição do valor do atributo classificado como readonly só acontece dentro da classe ou dentro do construtor.

```
class Employee {
    readonly empCode: number;
    empName: string;
    
    constructor(code: number, name: string)     {
        this.empCode = code;
        this.empName = name;
    }
}
``` 
#### private
 - define um atributo como **private**, ou seja, esse atributo não pode ser acessado pelo código fora da classe onde foi declarado. 
```
class Employee {
    private empCode: number;
    empName: string;
}
```


### Omit 
 - deixa de selecionar um atributo de um objeto, por exemplo.
 - A sintaxe é Omit<Type, Keys>
```
    interface Todo {
      title: string;
      description: string;
      completed: boolean;
      createdAt: number;
    }
     
    type TodoPreview = Omit<Todo, "description">;
     
    const todo: TodoPreview = {
      title: "Clean room",
      completed: false,
      createdAt: 1615544252770,
    };
```








