# 03-estudos-css

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

### LINKS DE VÍDEO CURSO E DOCUMENTAÇÃO

- <a href="https://www.w3schools.com/cssref/">Documentação CSS w3schools</a>
- <a href="https://developer.mozilla.org/pt-BR/docs/Web/CSS">Documentação CSS Mozilla developer</a>
- <a href="https://www.youtube.com/watch?v=5PS6ku8NzIE&list=PLirko8T4cEmx5eBb1-9j6T6Gl4aBtZ_5x"> Vídeo completo sobre display, Float e Position</a>

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
`border-radius: 10px;` // para suavizar a borda (arrendodar)  
`border-style: dotted;` // borda pontilhada  
`border-style: dashed;` // borda tracejada  
`border-style: none;` // aqui a borda é retirada  
`border-style: hidden;` // o elemento está na tela mas não esta aparecendo na página  
`border: 20px dashed red;` // Para criar uma borda de forma simples <br><br>
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

Cada adição de BORDER, PADDING e MARGIN, modifica o tamanho do elemento para fora do elemento e para não modificar o tamanho do elemento com estas adições vamos colocar um `box-sizing: border-box`, onde vai ajustar tudo para dentro do elemento.

```
    <style>
        .container01{ <!-- aqui vamos ter um quadrado de 120px -->
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

            box-sizing: border-box; <!-- Vai manter os 100px e jogar toda diferença para dentro do elemento -->
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
`width: 50vh;` unidade de medida em relção a modificação da altura da janela do html, porem o efeito é na largura  
`width: 50vmin` unidade de medida em relção ao menor tamanho da janela do html sendo altura ou largura  
`width: 40vmax;` unidade de medida em relção ao maior tamanho da janela do html sendo altura ou largura  
`width: 80%` unidade de medida em relção ao elemento "pai" baseando-se na %

#

### TEXT TRANSFORM E TEXT DECORATION

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform">Documentação text-transform AQUI</a><br /><br />
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration">Documentação text-decoration AQUI</a>

`text-align: center;` // Para centralizar na horizontal, podemos justificar para direita, esquerda, etc.  
`line-height: 100px;` // Para centratilar na vertical, vamos setar o tamanho de acordo com o tamanho do "pai"
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
        background-color: yellow; <!-- ":active" quando clica o link modifica de acordo com o determinado -->
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

#

### OVERFLOW

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow">Documentação AQUI</a>

`overflow: hidden;` // ele esconde o excesso e perdemos a informação que esta escondida.  
`overflow: auto;` // põe um scroll de acordo com a nescessidade, se precisar de scroll para os lados ele também vai por.  
`overflow: auto;` // coloca o scroll de acordo com a nescessidade  
`overflow-y: scroll;` // põe scroll no y
`overflow-x: hidden;` // esconde o scroll do x

#

### FLOAT

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/float">Documentação AQUI</a> <br>
<a href="https://www.youtube.com/watch?v=E1tR7sYMEN0&list=PLirko8T4cEmx5eBb1-9j6T6Gl4aBtZ_5x&index=4"> VÍDEO COMPLETO SOBRE FLOAT</a>

- FLOAT: é uma propriedade do display que permite que um lemento fique flutuando ao lado de outro elemento
- ele sempre cria um novo contexto então pode estar escondendo um elemento porem nunca fica sobre um conteúdo
- o "pai" que está guardando o elemento que está flutuando perde a largura e altura e a forma de corrigir é setar um `overflow: hidden` no elemento "pai"
- se os elementos que estão com o "float" não cabem mais na tela eles caem automaticamente um para baixo do outro
- quando não queremos que o próximo elemento fique atrás ou ao lado do elemento com o "float" vamos setar um `clear:;` no elemento para ele ir para um novo contexto

#

### POSITION

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/position">Documentação AQUI</a>

#### Position static e relative

<a href="https://www.youtube.com/watch?v=pMlxfhahXW4&list=PLirko8T4cEmx5eBb1-9j6T6Gl4aBtZ_5x&index=5"> VÍDEO COMPLETO SOBRE POSITION STATIC E RELATIVE</a>

🚧 _Porjeto EM CONSTRUÇÃO_ 🚧
