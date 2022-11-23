# 03-estudos-css

### LINKS DE VÍDEO CURSO E DOCUMENTAÇÃO

<a href="https://www.w3schools.com/cssref/">Propriedades do CSS</a>

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
`border: 20px dashed red;` // Para criar uma borda de forma simples <br>
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

###

🚧 _Porjeto EM CONSTRUÇÃO_ 🚧
