# Flux e Redux

## Flux 

 - Arquitetura para comunicação entre componentes.
 - Padrão de projeto para tráfego de dados de maneira unidirecional.
 - Usar o store para guardar somente os dados compartilhados entre os componentes.
 - Flux permite várias stores.
 - O dispatcher conecta as stores.
```
action -> dispatcher -> store -> view
```

## Redux

 - Dan Abramo e Andrew Clark (2015).
 - É uma implementação de flux.
 - É uma biblioteca que gerencia estados em aplicações JavaScript.
 - Pode ser usado com React, Angular, Vue e JS puro.
 - Centraliza o estado da aplicação.
 - Torna o fluxo de dados transparente e predizível.
 - É utilizado quando há necessidade de gerenciar os dados de uma aplicação.
 - Os dados que ele gerencia não são só os dados de entrada e de uma API, são, também, os dados de cliques, de mudança de páginas...
 - Controla como a aplicação deve se comportar baseada em ações do usuário.
 - Pode ser usado para compartilhar estados entre componentes.
 - redux-devtools é uma ferramenta para monitorar as alterações de estado da aplicação.
 - 3 princípios:
 - Single source of truth (store única)
 - State é read-only
 - Mudanças são feitas com pure functions (estado imutável)
 - Actions:
  - São como em flux
  - Um dos atributos de uma action é o **type**
  - o type recebe uma string ou uma constante.
  - Outro atributo é o **payload**
  - Não enviam a action em si para o dispatcher
  - É uma função que retorna um objetos
  - Retornam um objeto de action formatado
 - Store
  - Store única
  - Cuida de toda a árvore de estados
  - **Reducers** cuidam de descobrir qual estado mudou
 - Reducers
  - São funções puras, pois não têm efeito colateral.
  - Recebem parâmetros e retornam parâmetros.
  - Não existe dispatcher
  - Store se conecta ao **root reducer**, que divide os estados em pequenos reducers para gerenciá-los.
  - Os estados são imutáveis.
  - Descrevem como as actions transformam o estado em outro estado.
  - Recebe informações sobre os estados atuais e actions sobre aquele estado e retornam um novo estado.
  - A ideia é que haja um reducer para cada atributo do estado. 

```

// produtos recebe o estado anterior de produtos
{
	produtos: function(estadoAnterior, acao) {
		/* lógica e um return */
		return proximoEstado;
	},

// autenticacao recebe o estado anterior de autenticacao
	autenticacao: function(estadoAnterior, acao) {
		/* lógica e um return */
		return proximoEstado;
	},
}
```

```
function reducer(state, action) {
	if(action.type === 'addNumber')
		return[novo estado]
}
```


- Views
  - Provider: wrapper da árvore de componentes.
  - connect(): função do react redux que facilita os componentes se conectarem à store.
  - selector: usado para definir quais estados do redux devem ser passados como props.
 - A função do reducer é receber um objeto que representa o estado “anterior” da aplicação e baseado na ação que foi realizada, retornar um objeto completamente novo que tenha copiando todas as informações do estado anterior (no caso da tarefa, suas as chaves text e id) e atualizando apenas as propriedades necessárias
 
- Passo a passo 
  - Desenhar a store (o que armazenar?)
  - Definir as actions (que ações o usuário pode realizar na aplicação?)
  - Criar os reducers (recebem a action e devolvem o estado atualizado)
  - Atualizar a store










