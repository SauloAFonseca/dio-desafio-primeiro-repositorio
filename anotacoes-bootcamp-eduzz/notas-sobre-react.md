# ReactJs

## Essencial
- React é uma **biblioteca** open-source, baseada em componentes e declarativa para criação de interfaces de usuário.
- Criada e mantida pelo Facebook (hoje Meta).
- tudo que o usuário puder acessar estará dentro da pasta public: imagens, index.html...
- pasta src é o coração da aplicação, dentro dela ficam os códigos que cuidam da regra do negócio.
- No React, para definir uma classe dentro de um elemento HTML, usa-se "className".


```
// Comandos essenciais

npm init
npm install --save react@16.8.6 react-dom@16.8.6 react-scripts@3.0.1
npm start
npx create-react-app <nomeProjeto>
```

## Componentes
- São funções JavaScript.
- Permitem reutilização de partes do código.

## Package.json
- Usado parar armazenar metadados associados ao projeto.
- Contém as dependências, scripts, configurações do projeto.
- Torna fácil o gerenciamento e a instalação de outros pacotes no projeto.
- Em dependências, dentro do package.json, há a lista de pacotes instalados e suas versões. 
- No package, o atributo private é marcado como true para evitar a publicação de repositórios privados.
- Para adicionar um pacote nas dependências, é preciso usar --save.

```
npm install <package-name> --save
```

## Renderização
- Render é uma funcionalidade do React para agir sobre elementos HTML.
- React DOM é responsável por atualizar um elemento DOM.
- O propósito da função render() é mostrar um código HTML dentro de um elemento HTML específico.
- Dentro do HTML há um elemento, uma div, com id root. É o nó raiz e tudo dentro dela será gerenciado pelo reat DOM.
- A página HTML possui o DOM, mas o ReatJs não trabalha em cima desse DOM diretamente. Ele utiliza um Virtual DOM.
- Se houver uma alteração em uma parte do DOM, o React identifica qual parte foi alterada e atualiza aquele trecho específico.
- A alteração de trechos específicos do DOM virtual pelo React evita erros e dá ganho de perfomance.
- O ReactDOM.render() recebe dois argumentos: o código HTML e o elemento HTML.

```
import ReactDOM from "react-dom"


const rootElement = document.getElementeById("root")
ReactDOM.render(element, rootElement)
```

```
import ReactDOM from "react-dom"


const bloco = 
<div>
	<h1>Aprender Renderização</h1>
	<p></p>
</div>

ReactDOM.render(
	bloco,
	document.getElementById("root")
)
```
- Para renderizar várias tags de uma vez só, é preciso encapsular as tags filhas dentro de uma tag pai.

```
const element = <div>
                   <h1>This is Heading 1 < /h1>
                   <h2>This is Heading 2</h2 >
                   <h3>This is Heading 3 < /h3>   
                </div > ;
ReactDOM.render(
    element,
    document.getElementById("root"));
```

```
Renderização Condicional com &&

const buttonCustomer = <button>Historico do Cliente</button>
const hasCustomer = false
const App = () => {
	return (
		<div>
			{hasCustomer && (    
				<div>
					Clique no botão.
					{buttonCustomer}
				</div>
			)};
		</div>
	);
};
```

```
import React from 'react';
import ReactDOM from 'react-dom';

class Componente extends React.Component {
	constructor(props) {
		super(props);
		this.state = {exibir:false};

	alterarState = () => {
		let converter = !this.state.exibir;
		this.setState({exibir:converter});
	}

	render() {

		let meuTexto = "";
		if(this.state.exibir==true) {
			meuTexto = <h1>Olá, mundo!"</h1>;
		} else {
			meuTexto = " "
		}

		return(
			<div>
				{meutexto}
				<button onClick = {this.alterarState}>Clique Aqui</button>
			</div>

ReactDOM.render(<Componente />, document.getElementById('root'));
```

## JSX
- JavaScript com XML.
- O seu uso é opcional.
- Padrão de escrita que o React recomenda e que diminui a quantidade de código escrito.
- JSX usa a palavra "className" para definir uma classe, pois evita incompatibilidades com o "class" usado em códigos HTML comuns.

```
import React from 'react';
import ReactDOM from 'react-dom';

//Sem JSX
const elemento = React.creatElement('h1',{},'Elemento sem JSX');
ReactDOM.render(elemento, document.getElementById('root'));

//Com JSX
ReactDom.render(<h1>Elemento com JSX</h1>, document.getElementById('root'));
```

- Para inserir um código em JavaScript puro dentro de um código escrito em JSX, é preciso colocá-lo dentro de chaves {...}.

```
import React from 'react'
import ReactDOM from 'react-dom'

const nome = "Fulano de Tal";

const elemento = <h1>Olá, { nome }! Bem-vindo ao nosso website!</h1>;
ReactDOM.render(elemento, document.getElementByID('root');
```
- Para inserir um atributo em JSX usa-se o prefixo "data-".

```
import React from 'react'
import ReactDOM from 'react-dom'

const elemento = <h2 data-atributoExemplo="exemplo>Este trecho é um escrito....</h2>
ReactDOM.render(elemento, document.getElementById('root)
```
 
## Estado
- O estado do componente é similar às props, mas é privado e controlado pelo componente.
- A alteração no estado pode ou não ser fruto da interação com o usuário.
- State é um valor que tem relação com valores dinâmicos.
- O estado é atualizado comumente por eventos de teclado ou mouse.
- Quando o state é atualizado, o componente é renderizado novamente.
- O estado é apenas local ao componente e caso seja necessário enviar algum atributo para outro componente, isso é feito via props.
- Uma variável comum, quando alterada, não atualiza o componente.
- É uma propriedade do componente onde colocamos dados que, quando mudados, devem causar uma nova renderização.
- O state é configurado dentro do componente.
- Define-se o state como uma variável após as definição de uma classe.
- Usa-se o render( ) para lidar com o state.
- O state é acessado através da variável "this.state".
- Tamanho do state dos componentes afeta a performance do aplicativo.
- É importante diminuir o uso do state para ele não afetar a aplicação.
- O estado é imutável, ou seja, ele nunca deve ser alterado e sempre deve ser sobreposto.
- Para atualizar o estado,  basta utilizar a função setState em qualquer parte do componente e dessa forma repassamos apenas as variáveis que iremos atualizar no estado, deixando de lado qualquer outra informação que não iremos modificar.
- Um estado pode ser:
	- Inicialização
	- Montagem
	- Atualização
	- Desmontagem
- Estado são usados em componentes de classe e em componentes funcionais(nesse, é preciso usar React Hooks: useState e outros métodos).

```
import React from 'react';
import ReactDOM from 'react-dom';

// Componente
class Componente extends React.Component {
	//Construtor
	constructor(props){
		super(props);
		this.state = {nome:"Fulano"};
	}
	//Render
	render() {
		return <h1>{this.state.nome}</h1>
	}
}
// Render
ReactDOM.render(<Componente />, document.getElementById('root');

```
- Estados não podem ser alterados diretamente. É preciso usar o método "setState".

```
// Modo inválido de atualizar o estado
this.state.nome = "Beltrano" 

// Modo correto de atualizar o estado
this.setState({nome:"Beltrano"});
```

## Components
- São as partes de um sistema.
- Componentes em React retornam um pedaço de código JSX que informa o que deve renderizado na tela.
- O nome de um componente deve ser iniciado por letra maiúscula.
- Para renderizar um componente, é possível defini-lo como um nome definido pelo usuário e passá-lo como o primeiro argumento do ReactDom.render().

```
import React from 'react';
import ReactDOM from 'react-dom';


class ComponentName extends React.Component {
	render() {
		return <h1>Meu componente funciona!</h1>;
	}
}
ReactDOM.render(<ComponentName />, document.getElementById('root'));    // chama o componente criado antes
```
```
const Welcome=()=>
{ 
        return <h1>Hello World!</h1> 
} 
  
ReactDOM.render( 
    <Welcome />, 
    document.getElementById("root") 
); 
```
- Há dois tipos de componentes em React:
	- Funcionais
	- Classe
- Componentes funcionais são apenas funções JavaScript.
- Componentes funcionais podem ou não receber dados como parâmetros.
- Componentes de classe são uma forma de criar um componente baseado em classes. 
- É preciso usar o método "extends" parar criar um componente de classe e chamar "React.Component".
- É possível passar dados de um componente de  classe para outro componente de classe.

```
class Democomponent **extends** React.Component
{
    render(){
          return <h1>Welcome Message!</h1>;
    }
}

export default Democomponent;
```

## Props
- Props significa propriedades.
- É uma característica que o componente pode ter acesso: variáveis, constantes, funções etc.
- São componentes que você consegue transferir de um componente pai para um componente filho. 
- Props são argumento passados dentro de um componente. 
- Props são passados aos componentes através de atributos HTML.
- Funcionam como os argumentos de uma função ou os atributos de um HTML.

```
// Component
class Componente extends React.Component {
	render() {
		return <h1>Olá, {this.props.nome}</h1>;
	}
};

// Render
ReactDOM.render(<Componente nome="Fulano" />, document.getElementById('root');
```
- O atributo "nome" definido dentro da tag "Componente" no ReactDOM.render é um prop.
- o prop "nome" é usado no componente de classe "Componente". Para usá-lo, utiliza-se o "this.props.nome". O "this" informa que uma característica do componente está sendo usada, essa característica é o "props" e o props usado é o "nome".

## Webpack
- É um empacotador de módulos (module bundler).
- Webpack busca os arquivos dentro da pasta "src", dentro dessa pasta, ele busca inicialmente o "index.js"
- Internamente, o webpack mapeia todos os modulos que o projeto precisa e devolve um pacote com todos juntos.
- Webpack suporta:
	- fontes
	- CSS
	- imagens
	- HTML
	- JavaScript
	- plugins
- Principais conceitos de webpack:
	- Entry
	- Output
	- Loaders
	- Plugins
	- Mode

- **Entry**: O webpack precisa saber onde ele irá buscar todos os arquivos que precisa para criar o arquivo unificado
- **Output**: o webpack determina quais são os módulos que ele vai exportar para o arquivo final, que pode ser um ou mais arquivos.
- **Loaders**: permitem que o webpack gerencie arquivos que não são JavaScript, como CSS, HTML, imagens...
- **Plugins**: podem ser usados para otimização de pacotes, minificação, injeção de scripts...
- **Mode**: configuração dos módulos como **production**, **development** ou **none**.
- Modo Production traz otimizações internas
- Modo **Development** é executado com 3 plugins: 
	- UglifyjsPlugin
	- ModuleConcatenationPlugin
	- NoEmitOnErrosPlugin
- Modo None é usado quando não se quer passar configuração nenhuma.

```
Criação do arquivo **webpack.config.js**

1) npm i -D webpack webpack-cli //instala o webpack no diretório
2) "build": "webpack --mode production" // "start": "webpack --mode development"
3) npm i @babel/core-loader @babel/preset-env @babel/preset-react --save-dev

```

## EsLint
- Evita erros que possam ocorrer em tempo de desenvolvimento.

```
npm install --save-dev eslint babel-eslint eslint-plugin-react eslint-watch
```

## Listas e Chaves
- As listas são criadas de modo similar ao JavaScript.
- A função map( ) é usada para percorrer as listas.
- Cada elemento filho é uma lista necessita de uma chave única, por isso o uso de "key".
- **Key** é um atributo especial de uma string que é necessário à criação de de listas em React.
- Key identifica de forma única cada item de uma lista

```
import React from 'react';
import ReactDOM from 'react-dom';

class Components extends React.Component {
	render() {
		let cores = ["amarelo", "preto", "rosa"]
		let listar = cores.map((cor, index) =>{
			return <li key={index}>{index} - {cor}</li>
		});
		return (
			<ul> {listar} </ul>
		)
	}
}
ReactDOM.render(<Componente>, document.getElementById('root'));
```

## Eventos
- Semelhante a manipular eventos em elementos DOM.
- Eventos em React são nomeados com camelCase.
- O JSX é usado para passar uma função como manipulador de eventos no lugar de um texto.

```
// Captura evento do mouse

import React from 'react';

const showEvent = ( ) => {
	console.log('evento disparado')
};
const Button = <button onClick=(showEvent)>Mostrar Evento</button>
const App = () => {
	return(
		<div>
			{Button}
		</div>
	);
};
export default App;
```
```
// Captura eventos do teclado

import React from 'react';

teclado = (e) => {
	console.log(e.target.value);
};
render() {
	return(
		<div>
			<input type="text onChange={this.teclado} />
		</div>
	);
};
export default App;
```


