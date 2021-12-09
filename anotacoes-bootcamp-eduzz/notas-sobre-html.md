# Notas de aula sobre HTML

## Estrutura HTML

 - Tim Berns-Lee: criação do html.

 - HTML define o significado e a estrutura do conteúdo da web.

 - Uma tag pode ter atributos ou não.

 - A tag meta contém informações que navegadores e buscadores interpretam.

 - "!DOCTYPE html", apesar de parecer um elemento HTML, apenas diz ao navegador que ele está lidando com um arquivo do tipo HTML5.

 - O ideal é que haja somente uma tag h1 por página.

 - A tag "p" representa um parágrafo, mas ela não suporta apenas texto. Podemos adicionar imagens, código, vídeos e vários outros tipos de conteúdo.

 - A tag "a" significa anchor(âncora), ele representa um hyperlink. É ela que interliga vários conteúdos e páginas na web.

 - O href representa o hyperlink para onde sua âncora aponta.

 - Target neste momento vai servir para nos ajudar a abrir nossos links em outra aba do navegador.

## Tags semânticas:

 -  A semântica permite descrever mais precisamente o conteúdo.
 -  A tag div era o padrão de escrita do html, mas foi substituída pelas tags da web semântica.
 - Exemplos de tags semânticas:
 
     - **section**: seção genérica de conteúdo quando não houver um elemento mais específico.
     - **header**: cabeçalho da página ou de uma seção da página e normalmente contém logotipos, menus, campos de busca.
     - **article**: conteúdo independente e de maior relevância dentro de uma página. Pode conter outros elementos, como header, cabeçalhos, parágrafos e imagens.
     - **aside**: seção que engloba conteúdos relacionados ao conteúdo principal. Normalmente são representadas como barras laterais.
     - **footer**: representa o rodapé do conteúdo ou de parte dele, pois ele é aceito dentro de vários elementos, como article e section e até do body.

## Textos e Links:

#### Tags de texto:
 - Os elementos h1-h6 são importantes para nos indicar visualmente a importância e a localização e as seções de texto na página.
 -  Tags de texto:
     - **h1**: título da página.
     - **h2**: título da seção.
     - **h3**: título de artigo.
     - **p**: conteúdo do artigo.

#### Tags de link:
 - Exemplos de tags de link:
     - **a**: âncora que interliga os conteúdos.
     - **href**: link para onde a página está apontando (se for e-mail, adicione o atributo "mailto:fulano@email.com". Se for telefone, adicione "tel:").
     - **target**: indica como o link será aberto (nova aba ou nova janela).

## Imgens:

 - Utiliza a tag img.
 - Tag img não tem tag de fechamento.
 - Atributos da tag "img":
     - **src**: indica a fonte da imagem (interna ou externa a sua máquina).
     - **alt**: escreve um texto alternativo, caso a imagem não carregue e melhora a acessibilidade com leitores de tela.

## Listas:

 - Listas agrupam itens.
 - Exemplos de tags de lista:
     - **ul**: unordered list é uma lista na qual a ordem dos elementos não importa.
     - **ol**: ordered list é uma lista na qual a ordem dos elementos é importante. Ordena por números, letras ou algarismos romanos.
     - **li**: item list é o item da lista.
