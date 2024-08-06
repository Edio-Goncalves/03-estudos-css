# 03-estudos-css

Este repositório contém todos os recursos, exemplos e notas que compilei enquanto aprendia CSS. Meu objetivo é fornecer uma referência útil e prática a partir do que aprendi e documentar meu próprio progresso.

### ÍNDICE

- [CSS INLINE, INTERNO e EXTERNO](#css-inline-interno-e-externo)
- [CLASS (.) e ID (#)](#css-inline-interno-e-externo)
- [BORDER, MARGIN E PADDING](#border-margin-e-padding)
- [BOX MODEL](#box-model)
- [UNIDADES DE MEDIA](#unidades-de-media)
- [TEXT TRANSFORM E TEXT DECORATION](#text-transform-e-text-decoration)
- [FONT](#font)
- [ESTILO DE LINK](#estilo-de-link)
- [ESTILO DE LISTAS](#estilo-de-listas)
- [DISPLAY](#display)
- [OVERFLOW](#overflow)
- [FLOAT](#float)
- [POSITION](#position-posicionamento-verticalx-e-horizontaly)
- [RESPONSIVIDADE E MEDIA QUERIE](#responsividade-e-media-querie)
- [SELETORES](#seletores)
- [PSEUDO ELEMENTOS](#pseudo-elementos)
- [PSEUDO CLASSES](#pseudo-classes)
- [FUNÇÃO CALC](#função-calc)
- [TRANSFORM](#transform)
- [VARIAVEL](#variavel)
- [RESET](#reset)

### LINKS DE VÍDEO CURSO E DOCUMENTAÇÃO

- <a href="https://www.w3schools.com/cssref/">Documentação CSS w3schools</a>
- <a href="https://developer.mozilla.org/pt-BR/docs/Web/CSS">Documentação CSS Mozilla developer</a>
- <a href="https://www.youtube.com/watch?v=5PS6ku8NzIE&list=PLirko8T4cEmx5eBb1-9j6T6Gl4aBtZ_5x"> Vídeo completo sobre display, Float e Position</a>
- <a href="https://www.youtube.com/watch?v=Gu-IPxZux-w">Vídeo explicativo de todos seletores</a>

#

### CSS INLINE, INTERNO e EXTERNO

#### CSS inline

É quando colocamos o CSS no "body" da página, abrimos um "style" na "tag" e colocamos a propriedade css.

```
    <p style="color: red">
          O style está dentro do <p>
    </p>
```

#### CSS interno

É quando colocamos o CSS no "head" da página, abrimos um "style" e colocamos as propriedade css dentro.

```
    <head>
        <style>
            body{
                background-color: black;
            }
        </style>
    </head>
```

#### CSS externo

Criamos um novo arquivo chamado "style.css" onde linkamos ao nosso head para ser a fonte da nossa estilização em CSS.

```
    <head>
        <link rel="stylesheet" href="style.css" />
    </head>
```

#

#### CLASS (.) e ID (#)

<a href="https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Type_Class_and_ID_Selectors">Documentação AQUI</a>

- Vamos criar identificadores para colocar nos elemento ondem compõem a
  mesma "tag". Ex: tenho 4 paragrafos mas quero modificar apenas o estilo
  de um deles.
- O ID é identificado com "#", já a class com ".", quando não colocamos
  nada o CSS tenta encontrar uma "tag" no HTML.

- O ID podemos usar em apenas um elemento, já a class podemos usar em
  vários elementos, então quando precisarmos repetir a estilização vamo
  usar class.

```
<style>
    .cor01{
        color: red;
    }
    #parag{
        color: blue;
    }
</style>

<html>
<body>
    <p> Parágrafo 01</p>
    <p class="cor01"> Parágrafo 02</p> <!-- colocamos uma "class" no <p> -->
    <p id="parag"> Parágrafo 03</p> <!-- colocamos um "id" no <p> -->
    <p> Parágrafo 04</p>
</body>
</html>
```

#

### BORDER, MARGIN E PADDING

#### Border

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border">Documentação border AQUI</a>

`border-width: 1px;` // para dar espessura para a borda  
`border-style: solid;` // linha solida na borda  
`border-color: blue;` // colorir a borda  
`border-color: transparent;` // deixa a borda transparente, bom para usar com o ":hover"  
`border-radius: 10px;` // para suavizar a borda (arrendodar)  
`border-style: dotted;` // borda pontilhada  
`border-style: dashed;` // borda tracejada  
`border-style: none;` // aqui a borda é retirada  
`border-style: hidden;` // o elemento está na tela mas não esta aparecendo na página  
`border: 20px dashed red;` // Para criar uma borda de forma simples  
`border-image-source: url();` // Para colocar uma imagem na borda  
`border-image-width: 50px;` // Para criar o tamanho da largura onde vai entrar a imagem  
`border-image-slice: 30%;` // Para setar o recorte  
`border-image-outset: 50px;` // Para ajustar a margem da borda ao elemento para fora ou para dentro  
`border-image-repeat: round;` // Para mostrar a forma dos intervalos <br><br>  
Exemplo de uma borda com várias espessuras e cores:

```
    .borderVariasEspessuras{
        border-width: 5px 10px 15px 5px;
        border-style: solid;
        border-color: red black blue green;
    }
```

#### Margin e padding

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin">Documentação margin AQUI</a><br /><br />
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding">Documentação padding AQUI</a>
<br />

`margin: 10px;` // distância o elemento de outro elemento em todas direções  
`margin: auto;` // para centralizar na horizontal  
`margin-left: 5px;` // temos 4 direções, left, right, bottom e top  
`margin: 10px 3px ;` // topo + inferior, esquerda + direita  
`margin: 10px 3px 30px 5px;` // superior, direita, inferior e esquerda <br><br>

`padding: 20px;` // distância dentro do próprio elemento em todas direções  
`padding-top: 3px;` // temos 4 direções, left, right, bottom e top  
`padding: 5% 10%;` // vertical e horizontal  
`padding: 2px 1em 0 1em;` // superior, direita, inferior e esquerda

#

### BOX MODEL

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model">Documentação AQUI</a>

`box-sizing: content-box` // quebra o layout, estoura o tamanho do elemento, soma o tamanho do elemento e sua margin, padding e border
`box-sizing: border-box` // nao quebra o layout, limita o tamanho pela dimensão do elemento, jogar toda diferença para dentro do elemento

Cada adição de BORDER, PADDING e MARGIN, modifica o tamanho do elemento para fora do elemento e para não modificar o tamanho do elemento com estas adições vamos colocar um `box-sizing: border-box`, onde vai ajustar tudo para dentro do elemento.

```
<style>
    .container01{ <!-- aqui vamos ter um quadrado de 120px, 100px doelemento + 10px da borda + 10px do padding -->
        padding: 10px;
        width: 100px;
        height: 100px;
        border: 10px solid blue;
    }
    .container02{
        padding: 10px;
        width: 100px;
        height: 100px;
        border: 10px solid blue;

        box-sizing: border-box; <!-- Mantem 100px e jogar toda diferença p/ dentro do elemento -->
    }
</style>

<html>
<body>
    <div class="container01"></div>
    <div class="container02"></div>

</body>
</html>
```

#

### UNIDADES DE MEDIA

<a href="https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units">Documentação AQUI>

#### Unidades de medidas fixas

`width: 1cm;` centimetros  
`width: 5mm;` milimetros (10 milimetros = 1cm)  
`width: 1in;` polegadas (1 polegada = 2,54cm)  
`width: 10px;` pixel  
`width: 10pt;` ponto  
`width: 1pc;` picas (1 pica = 12pt)

#### Uidades de medidas de referência (Relativa)

`font-size: 4em;` valor de "em" é multiplicado pelo valor do elemento "pai"  
`font-size: 1rem;` valor de "rem" é multiplicado pelo valor do elemento "raiz"  
`width: 50vw;` unidade de medida em relção a modificação da largura da janela do html
`width: 50vh;` unidade de medida em relção a modificação da altura da janela do html
`width: 50vmin` unidade de medida em relção ao menor tamanho da janela do html sendo altura ou largura
`width: 40vmax;` unidade de medida em relção ao maior tamanho da janela do html sendo altura ou largura  
`width: 80%` ocupa a % de toda a area disponivel do elemento pai, levando em consideração margin

#

### TEXT TRANSFORM E TEXT DECORATION

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform">Documentação text-transform AQUI</a><br /><br />
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration">Documentação text-decoration AQUI</a>

_OBS: sempre que formos usar a forma resumida dos tamanho vamos pensar em sentido horário, topo, direita, inferior e esquerda_

`text-align: center;` // Para centralizar na horizontal, podemos justificar para direita, esquerda, etc.  
`line-height: 100px;` // Para criar uma linha com altura determinada e centralizar o texto na vertical  
`text-indent: 30px;` // identa o início de cada paragrafo  
`letter-spacing: 1.8px;` // espaço entre as letras  
`word-spacing: 15px;` // espaço entre as palavras  
`line-height: 30px;` // altura da linha fixada em pixels  
`line-height: 1.8;` // altura da linha multiplicando pelo tamanho da fonte  
`text-shadow: 2px 2px 5px black;` // deslocamento para direita, deslocamento para baixo, desfoque e cor <br> <br>

`text-transform: uppercase;` // caixa alta  
`text-transform: lowercase;` // todo em caixa alta  
`text-transform: capitalize;` // para por toda primeira letra de cada palavra em maiuscula <br> <br>

`text-decoration: underline;` // linha em baixo  
`text-decoration: line-through;` // riscado  
`text-decoration: overline;` // linha em cima  
`text-decoration: underline overline;` // da para aplicar mais de um text-decoration  
`text-decoration: none;` // para retirar o style padrão do link

#

### FONT

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font">Documentação AQUI</a>

`font-size:` // para mudar tamanho da fonte e podemos usar todas unidades de medidas nela  
`font-style: italic;` // Deixar a fonte em italico  
`font-weight: bold;` // colocar em negrito. Para estar modificando o negrito em valor, ex: "font-weight: 500;"  
`font-variant: small-caps;` //Coloca todas as letras em caixa alta mas respeita a letra maiúscula digitada  
`font-family: 'Times New Roman', Times, serif;` // Serif são cantos das fontes com pontas  
`font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;` //Sans-serif são fonte lisas e arredondadas  
`font-family: 'Courier New', Courier, monospace;` // Monospace são fonte onde todos os caracteres ocupam o mesmo espaço

#

### ESTILO DE LINK

<a href="https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Styling_links">Documentação AQUI</a>

```
<style>
    .link{
        text-decoration: none; <!-- tirar o sublinhado do link -->
        color: red;
        cursor: all-scroll; <!-- mudar o cursor -->
        padding: 10px; <!-- mudar o padding -->
        padding-bottom: 5px; <!-- mudar apenas padding inferior. No caso ele substitui o 10px por 5px -->
        border-radius: 10px; <!-- arredondar a borda -->
        border: 3px solid red; <!-- criar a borda -->
    }
    .link:visited{
        color: black; <!-- ":visited" para colorir o link após ser visitado -->
    }
    .link:hover{
        background-color: yellow; <!-- ":hover" quando ponho o mouse em cima ele muda a cor -->
        color: black;
    }
    .link:active{
        background-color: yellow; <!-- ":active" quando clica o link modifica de acordo com o pedido -->
        color: black;
    }
</style>

<html>
<body>
    <div>LINK 01</div>
    <div>LINK 02</div>
    <div>LINK 03</div>
<body>
</html>
```

#

### ESTILO DE LISTAS

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/list-style">Documentação AQUI</a>

Exemplos:

```
<style>
    .listUl{
        list-style-type: none; <!-- retirar a parte identificador defaul do elemento -->
    }
    .listUrl{
        list-style-image: url(./imagens/selecionarImagem; <!-- inserir imagem -->
        background-color: rgb(227, 205, 247);
    }
    .liPadrao{
        margin-bottom:  3px;
        background-color: aqua;
        border: 1px solid; <!-- para por as bordas das linhas -->
    }
    .liDentro{
        border: 1px solid; <!-- para por as bordas das linhas -->
        list-style-position: inside; <!-- Joga o simbolo para drentro da linha -->
    }
</style>


<html>
<body>
        <ul class="listUl">
          <li>item 1</li>
          <li>item 2</li>
        </ul>

        <ol class="listOl">
          <li>item 1</li>
          <li>item 2</li>
        </ol>

        <ul class="listUrl">
          <li class="liPadrao">item 1</li>
          <li class="liDentro">item 2</li>
          <li>item 3</li>
        </ul>
</body>
</html>

```

#

### DISPLAY

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display">Documentação AQUI</a>

Temos 4 display mais comuns:

`display:none;` // ele retira o elemento da tela, é como se nunca tivesse sido colocado lá  
`display:inline;` // fica na mesma linha, ele não vai fazer a quebra de linha, e não conseguimos colocar tamanho no elemento  
`display:block;` // preenche toda a largura da tela, ele vai fazer uma quebra de linha e jogar o próximo conteúdo para próxima linha. Com o `display:block;` podemos colocar tamanho (widht, height, etc.) no elemento  
`display:inline-block;` // ele vai manter o comportamento do `display:inline;` e vai deixar colocar largura e altura <br>

_OBS: Nunca podemos ter um elemento do tipo "block" dentro de um
parágrafo, ele quebra o fluxo!!!_

Explicação completa de `display:inline;` :
<a href="https://www.youtube.com/watch?v=5PS6ku8NzIE">Aprenda a display: inline;</a> <br>

Explicação completa de `display:block;` :
<a href="https://www.youtube.com/watch?v=HWfhwokS_qg">Aprenda a display: block;</a>

Explicação completa de `display:inline-block;` :
<a href="https://www.youtube.com/watch?v=Yj9-N9BEVeM">Aprenda a display: inline-block;</a>

#### Display flex

Trabalhamos com coluna OU linha

<a href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox">Documentação "display:flex" e "display:inline-flex";</a>  
<a href="https://www.youtube.com/watch?v=WyIiuB8NoqQ">FLEX BOX COMPLETO;</a>

`display:flex;` // para setar o comportamento de exibição dos elementos filhos, ele possibilita trabalhar em flex direction, podendo mudar o comportamento em coluna, linha, direção e espaçamento.  
`display:inline-flex;` // trabalha da mesma forma que o "display:flex" com os filhos mas muda o comportamento do container, fica igual o "display:inline"  
`flex-wrap:nowrap;` // para efetuar ou nao efetuar quebra de linha (nowrap, wrap, wrap-reverse)  
`flex:1 1 2;` // Define a proporsão dos itens dentro do container  
`flex-direction:row;` // é o padrão do "display:flex", os lementos ficam em linha  
`flex-direction:row-reverse;` // para inverter a ordem dos elmentos e o inicio dos elementos  
`flex-direction:column;` // para colocar os elementos em coluna  
`flex-direction:column-reverse;` // para inverter a ordem dos elmentos e o inicio dos elementos  
`justify-content: center;` // alinha todos os itens no eixo principal (flex-start, flex-end, space-between, space-around, stretch, space-evenly)  
`align-items: center;` // alinha todos itens no eixo transversal (flex-start, flex-end, stretch, baseline)  
`align-self: center;` // alinha individualmente no eixo transversal  
`align-content: center;` // define a distribuição entre os items do conteúdo do eixo transversal

#### Display grid

Trabalhamos com coluna E linha

<a href="https://www.youtube.com/watch?v=lh0qB15vRoo">YT - GRID COMPLETO;</a>  
<a href="https://www.youtube.com/watch?v=q_WV9exilhk&list=PLYgzkrmJnLwpeeGgdADYq3cE2yUwLLTOv">YT - GRID DETALHADO;</a>

`display:grid;` // para criar um grid  
`grid-template-columns: 1fr 1fr 1fr;` // para criar colunas no grid de forma explicita, podemos usar função "repeat" e "minmax" para construir o grid  
`grid-template-rows: repeat(4, 1fr);` // para criar linhas no grid de forma explicita, podemos usar função "repeat" e "minmax" para construir o grid  
`grid-column-gap: 5px;` // para modificar a distancia apenas das colunas do grid  
`grid-row-gap: 5px;` // para modificar a distancia apenas das linhas do grid  
`grid-gap: 10px;` // para modificar a distancia entre as linhas e colunas do grid  
`grid-auto-rows: 100px ;` // para setar o tamanha das linha implicitas, qualquer novo elemento adicionado  
`grid-auto-columns: 100px ;` // para setar o tamanha das colunas implicitas, qualquer novo elemento adicionado  
`align-items: strech;` // (start, center, end, strech)  
`justify-items: strech;` // (start, center, end, strech)  
`align-self: strech;` // Usa-se no proprio item e nao no container do grid (start, center, end, strech)  
`grid-column: 1 / -1;` // usamos para setar o inicio e o fim da coluna do elemento em relação ao grid  
`grid-row: 1 / 3;` // usamos para setar o inicio e o fim da linha do elemento em relação ao grid  
`grid-template-area: "header header aside aside";` // usamos para setar todo o template do grid baseado em identificadores, criando um mapa de coordenadas

#

### OVERFLOW

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow">Documentação AQUI</a>

`overflow: hidden;` // ele esconde o excesso e perdemos a informação que esta escondida.  
`overflow: auto;` // põe um scroll de acordo com a nescessidade, se precisar de scroll para os lados ele também vai por.  
`overflow-y: scroll;` // põe scroll no y  
`overflow-x: hidden;` // esconde o scroll do x

#

### OUTROS

`resize: both;` // para conseguir redimensionar uma elemento, igual o textarea (none, horizontal, vertical, etc.)  
`z-index: 2;` // "(OBS: position" não pode ser "staick") é para organizar as camadas na perspectiva de visualização do usuario  
`order: 0;` // vamos usar para ordenar a posição dos elementos  
`cursor: auto;` // vamos usar para mudar o cursor

#

### FLOAT

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/float">Documentação AQUI</a> <br> <br>
<a href="https://www.youtube.com/watch?v=E1tR7sYMEN0&list=PLirko8T4cEmx5eBb1-9j6T6Gl4aBtZ_5x&index=4"> VÍDEO COMPLETO SOBRE FLOAT</a>

- FLOAT: é uma propriedade do display que permite que um lemento fique flutuando ao lado de outro elemento
- ele sempre cria um novo contexto então pode estar escondendo um elemento porem nunca fica sobre um conteúdo
- o "pai" que está guardando o elemento que está flutuando perde a largura e altura e a forma de corrigir é setar um `overflow: hidden` no elemento "pai"
- se os elementos que estão com o "float" não cabem mais na tela eles caem automaticamente um para baixo do outro
- quando não queremos que o próximo elemento fique atrás ou ao lado do elemento com o "float" vamos setar um `clear:;` no elemento para ele ir para um novo contexto

#

### POSITION (Posicionamento vertical(x) e horizontal(y))

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/position">Documentação AQUI</a>

#### Position static e relative

<a href="https://www.youtube.com/watch?v=pMlxfhahXW4&list=PLirko8T4cEmx5eBb1-9j6T6Gl4aBtZ_5x&index=5"> VÍDEO COMPLETO SOBRE POSITION STATIC E RELATIVE</a>

#### Position absolute

<a href="https://www.youtube.com/watch?v=f8H-wstL0nU&list=PLirko8T4cEmx5eBb1-9j6T6Gl4aBtZ_5x&index=7"> VÍDEO COMPLETO SOBRE POSITION ABSOLUTE</a>

#### Position fixed

<a href="https://www.youtube.com/watch?v=e41QFmkqaEY&list=PLirko8T4cEmx5eBb1-9j6T6Gl4aBtZ_5x&index=8"> VÍDEO COMPLETO SOBRE POSITION FIXED</a>

#

### RESPONSIVIDADE E MEDIA QUERIE

<a href="https://www.youtube.com/watch?v=H91DhKPjhPk">VÍDEO COMPLETO SOBRE RESPONSIVIDADE</a>

- Uma forma para trabalhar com a responsividade em uma DIV é utilizando % em width e height
- Para trabalhar com responsividade de DIV dentro de uma DIV vamos usar o alinhamento vertical de position + transform
- Também conseguimos trabalhar a responsividade de texto com "font-size: 6em" como um exemplo

Layout Fluído: <br>

- `%` // Porcentagem (pega toda area disponivel do pai,)
- `auto` // Automática
- `vh` // Viewport height
- `vw` // Viewport width (pega em relação a janela, ele vai ignorar margin, cuidado ao usar)

Textos Fluídos: <br>

- `em` // Multiplicado pelo pai
- `rem` // Multiplicado pelo root

#### Media Querie

Vamos usar o "media querie" para poder trabalhar a responsividade da página pelo CSS. <br> <br>
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries">Documentação MEDIA QUERIE AQUI</a> <br>

```
@media screen and (max-width: 630px) {
    header{
        font-size: 10px
    }
}

@media screen and (max-width: 980px) {
    header{
        font-size: 12px
    }
}
<!-- Os "media querie" devem ser sempre do menor para o maior -->
```

#

### SELETORES

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors">Documentação AQUI</a> <br> <br>
<a href="https://www.youtube.com/watch?v=Gu-IPxZux-w">VÍDEO EXPLICATIVO DE TODOS SELETORES</a>

Os seletores tem prioridades de importância, se tivermos dois seletores modificando um mesmo elemento ele irá dar prioridade por importância <br>

1. IDs
2. Classes, attributes e pseudo-classes
3. Elements e pseudo-elements

<a href="https://specificity.keegan.st/">CALCULADORA DE PRIORIDADE DE SELEÇÃO</a>

Formas de selecionar:
`*{};` // seletor universal <br>
` #numb{}` // seleção por "ID" <br>
` .nome{}` // seleção por "classe" <br>
`p{};` // seleção por "tag" <br>
`#head01 p{};` // vai pegar todos os "p" dentro da "ID" <br>
`#head01 > p{};` // vai selecionar os "p" filhos do "ID" <br>
`#head01 + p{};` // vai selecionar o primeiro irmão do "p" dentro do "ID", se o próximo elemento não for um "p" ele não pegará <br>
`#head01 ~ p{};` // irá pegar todos irmãos do "p" dentro da "ID" <br>
`p[href]` // vai selecionar o "href" dentro do "p", se tiver mais de um "p" com "href" ele vai selecionar <br>
`[width]{};` // selesionar todos atributos "width" <br>
`[width="350px"]{};` // selesionar pelo atributo e seu valor <br>
`[title~="identificador"]{};` // selesionar todos os "title" que tenham a palavra "identificador" <br>
`[title^="i"]{};` // selesionar todos os "title" que comecem com a letra "i" <br>
`[title*="i"]{};` // selesionar todos os "title" em qualquer lugar que comece com a letra "i" <br>
`[title$="0"]{};` // selesionar todos os "title" que terminem com o numero "0" <br>

#

### PSEUDO ELEMENTOS

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements">Documentação AQUI</a>

`::before` // Para modificar antes do conteúdo <br>
`::after` // Para modificar depois do conteúdo <br>
`::first-line` // Para modificar a primeira linha <br>
`::first-letter` // Para modificar a primeira letra <br>
`::selection` // Para modificar quando selecionado <br>
`::placeholder` // Para modificar o "placeholder" <br>

Exemplo de como adicionar um icone em uma lista:

```
<style>
    #icon li::before{
        content: ""; <!-- criei um espaço para ser utilizado pelo contúdo a ser adicionado-->
        display: inline-block; <!-- deixei ele ter algo do lado -->

        width: 25px; <!-- criei o tamanho do espaço -->
        height: 25px;
        background-image: url(./imagens/g_icon.png); <!-- inseri uma imagem de fundo -->
        background-repeat: no-repeat; <!-- a imagem não pode repetir -->
        background-size: cover; <!-- a imagem tem que cobrir tudo -->
        transform: translateY(25%); <!-- ajustei a posição da imagem em relação ao eixo y -->
    }
</style>

<html>
<body>
    <ul id="icon">
        <li>item 10</li>
        <li>item 20</li>
        <li>item 30</li>
    </ul>

</body>
</html>
```

#

### PSEUDO CLASSES

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes">Documentação AQUI</a> <br> <br>

`:hover{};` // quando passar o mouse sobre o elemento ele aplica a estilização <br>
`:active{};` // quando clicarmos iremos ativar e a modificação irá ser aplicada <br>
`:nth-of-type(odd){};` // Para modificar os pares <br>
`:nth-of-type(even){};` // Para modificar os impares <br>
`:focus{};` // Põe o foco onde está selesionado <br>
`:first-of-type{};` // Para modificar o primeiro tipo do imputado <br>
`:first-child{};` // Para modificar o primeiro filho <br>
`:nth-child(3){};` // Para modificar a posição escolhida" <br>
`:nth-of-type(2n){};` // Para modificar de 2 em 2 <br>
`:nth-of-type(3n + 1){};` // Para modificar de 3 em 3 e também o primeiro <br>
`:not(:first-child){};` // Para deixar algum elemento de fora, para criar exceção. No exemplo estamos pega tudo menos o primeiro filho do elemento <br>

Exemplo de como adicionar um cores alternadas em uma lista:

```
<style>
    #listas li:nth-of-type(odd){   <!-- para pegar os pares -->
        background-color: beige;
    }
    #listas li:nth-of-type(even){   <!-- para pegar os impares -->
        background-color: gray;
        color: white;
    }
</style>

<html>
<body>
        <ul id="listas">
          <li>Item 0</li>
          <li>Item 1</li>
          <li>Item 2</li>
          <li>Item 3</li>
        </ul>

</body>
</html>
```

#

### FUNÇÃO CALC

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/calc">Documentação AQUI</a> <br> <br>
<a href="https://www.youtube.com/watch?v=TZgmjIBmdXc">VÍDEO DE EXEMPLO DE UTILIZAÇÃO </a>

`+` adição <br>
`-` subtração <br>
`*` multiplicação. Pelo menos um dos argumentos deve ser um número <br>
`/` divisão. O operador da direita deve ser um número <br>

Exemplos:
` width: calc(50% - 20px)` <br>
` height: calc(33,33% - 2em)` <br>

#

### TRANSFORM

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform">Documentação AQUI</a>

`transform: rotate(45deg);` // para rotacionar em graus <br>
`transform: scale(0.5, 0.9);` // para configurar uma escala (1 = 100%) <br>
`transform: skew(40deg, 20deg);` // para dar direção as pontas <br>
`transform: rotate(45deg) scale(0.8) skew(-30deg);` // podemos usar mais de um transform

#

### VARIAVEL

<a href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/var">Documentação AQUI</a> <br> <br>
<a href="https://www.youtube.com/watch?v=hRSi5rYtCj8"> VÍDEO DE EXEMPLO DE COMO USAR VARIÁVEIS</a>

Exemplo de como adicionar um cores alternadas em uma lista:

```
<style>
    :root{  <!-- root é o HTML, aqui estamos dizendo para qualquer css ter acesso ao conteúdo -->
        --var_color_first: red; <!-- aqui criamos uma variável com a cor vermelha -->
        --var_color_second: blue; <!-- aqui criamos uma variável com a cor azul -->

        --square-size: 100px; <!-- aqui criamos uma variavel com um size -->
    }

.p2{
    color: var(--var_color_first); <!-- aqui puxamos a variável e aplicamos onde queremos -->
    font-size: 25px;
}
.p3{
    color: var(--var_color_second);  <!-- aqui puxamos a variavel e aplicamos onde queremos -->
    font-size: 15px;
}
.sqr01{
    width: var(--square-size);
    height: var(--square-size);
    background-color: black;
}

<!-- podendo modificar sempre que quiser e tendo o efeito aplicado no elemento que utilizou a variável -->

```

#

### RESET

<a href="https://meyerweb.com/eric/tools/css/reset/">Documentação AQUI</a> <br> <br>
<a href="https://www.youtube.com/watch?v=23G_3ODk5mY">VÍDEO EXPLICATIVO DO RESET</a>

```
/* http://meyerweb.com/eric/tools/css/reset/
   v2.0 | 20110126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed,
figure, figcaption, footer, header, hgroup,
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure,
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
```

#

🚧 _Projeto EM CONSTRUÇÃO_ 🚧
