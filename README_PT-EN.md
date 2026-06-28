# Strudel Visuals v1 (Experimental)

**Strudel Visuals** é uma biblioteca experimental que cria uma camada gráfica baseada em **HTML5 Canvas 2D** para o **Strudel REPL**.

Ela transforma padrões musicais do Strudel em animações gráficas sincronizadas, permitindo controlar posição, cor, geometria e comportamento visual diretamente a partir de Patterns.

A biblioteca ainda está em desenvolvimento e a API pode mudar nas próximas versões.

---

# Instalação

Importe o script no início do código:

```javascript
await import(
  "https://kassurin.codeberg.page/scripts-para-live-coding/visuals-v1.js"
)
```

Depois disso, a função `.visuals()` estará disponível para qualquer camada do Strudel.

---

# Uso

```javascript
.visuals(

  grid(

    cells,
    cols,
    rows,
    showGrid,
    colors,

    shape({

      sides,
      radius,
      roundness,
      rotation,
      stroke,
      gain,
      decay

    })

  )

)
```

---

# grid()

Organiza a tela em células.

```javascript
grid(
    cells,
    cols,
    rows,
    showGrid,
    colors,
    shape(...)
)
```

## Parâmetros

### cells

Pattern do Strudel que define quais células serão ativadas.

Exemplos

```javascript
"0 1 2 3"

rand.range(0,15)

sine.range(4,9)
```

---

### cols

Número de colunas.

---

### rows

Número de linhas.

---

### showGrid

Mostra ou esconde a grade.

```javascript
true
false
```

---

### colors

Define as cores da camada.

Cores CSS seguem a sintaxe do Tidal/Strudel:

```javascript
"red cyan yellow magenta"
```

Cores hexadecimais utilizam arrays JavaScript:

```javascript
[
 "#00ffff",
 "#ff0088",
 "#ffaa00"
]
```

---

# shape()

Define a geometria desenhada em cada célula.

```javascript
shape({

    sides:4,

    radius:20,

    roundness:0,

    rotation:45,

    stroke:3,

    gain:80,

    decay:0.93

})
```

## Parâmetros

### sides

Número de lados.

```text
3  triângulo

4  quadrado

5  pentágono

6  hexágono

...

64 ≈ círculo
```

---

### radius

Raio inicial.

---

### roundness

Suavização dos cantos.

No momento apenas

```javascript
0
```

e

```javascript
>=1
```

estão implementados.

---

### rotation

Rotação em graus.

Muito útil para quadrados e polígonos.

---

### stroke

Espessura inicial do contorno.

---

### gain

Expansão provocada por cada trigger.

---

### decay

Velocidade de desaparecimento da animação.

Valores maiores mantêm a forma ativa por mais tempo.

---

# Exemplo

```javascript
t1:
s("bd")

.visuals(

grid(

"0 1 2 3",

3,

3,

false,

"red orange yellow",

shape({

sides:3,

radius:18,

stroke:2,

gain:80

})

)

)
```

---

# Estado do projeto

Este projeto é experimental.

A arquitetura ainda está sendo discutida e provavelmente mudará conforme novos recursos forem implementados.

Feedback, sugestões, relatórios de bugs e Pull Requests são muito bem-vindos.
****************************************************************************************

# Strudel Visuals v1 (Experimental)

**Strudel Visuals** is an experimental **HTML5 Canvas 2D** library for the **Strudel REPL**.

It converts Strudel musical Patterns into synchronized visual animations, allowing geometry, color and animation parameters to be controlled directly from live coding.

The API is still experimental and may change.

---

# Installation

Import the script:

```javascript
await import(
  "https://kassurin.codeberg.page/scripts-para-live-coding/visuals-v1.js"
)
```

The `.visuals()` function will then be available on every Strudel layer.

---

# Syntax

```javascript
.visuals(

grid(

cells,

cols,

rows,

showGrid,

colors,

shape({

sides,

radius,

roundness,

rotation,

stroke,

gain,

decay

})

)

)
```

---

# grid()

Defines the visual grid.

```javascript
grid(
cells,
cols,
rows,
showGrid,
colors,
shape(...)
)
```

## Parameters

### cells

Any Strudel Pattern selecting active cells.

Examples

```javascript
"0 1 2 3"

rand.range(0,15)

sine.range(4,9)
```

---

### cols

Number of columns.

---

### rows

Number of rows.

---

### showGrid

Show or hide the grid.

---

### colors

Layer colors.

CSS colors use the normal Tidal/Strudel syntax:

```javascript
"red cyan yellow"
```

Hexadecimal colors use JavaScript arrays:

```javascript
[
"#00ffff",
"#ff0088"
]
```

---

# shape()

Defines the geometry drawn inside each cell.

```javascript
shape({

sides:4,

radius:20,

roundness:0,

rotation:45,

stroke:3,

gain:80,

decay:0.93

})
```

## Parameters

### sides

Number of polygon sides.

```text
3 triangle

4 square

5 pentagon

6 hexagon

...

64 ≈ circle
```

---

### radius

Base radius.

---

### roundness

Corner smoothing.

Currently only

```javascript
0
```

and

```javascript
>=1
```

are implemented.

---

### rotation

Rotation in degrees.

---

### stroke

Initial stroke width.

---

### gain

Expansion produced by each trigger.

---

### decay

Animation decay.

Higher values keep the shape visible for longer.

---

# Example

```javascript
t1:
s("bd")

.visuals(

grid(

"0 1 2 3",

3,

3,

false,

"red orange yellow",

shape({

sides:3,

radius:18,

stroke:2,

gain:80

})

)

)
```

---

# Project status

This is an experimental project.

The architecture is still evolving and will likely change as new features are added.

Feedback, bug reports, API ideas and Pull Requests are highly appreciated.
