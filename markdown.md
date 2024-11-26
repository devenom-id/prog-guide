Dificultad: **Nula**

Tiempo estimado para aprenderlo: **Una tarde**
## Tabla de contenidos
- [Introducción](#introducción)
- [Texto](#texto)
- [Listas](#listas)
- [Bloques de código](#bloques-de-código)
- [Citas](#citas)
- [Enlaces y multimedia](#enlaces-y-multimedia)
- [Misceláneo](#misceláneo)

## Introducción

Markdown es un lenguaje de marcado.

Lenguaje de marcado en inglés es "Markup language".

Markdown se usa para crear fácilmente documentos en los que el texto puede ser formateado, se pueden añadir bloques de código, tablas, imagenes y videos.

Markdown puede aprovecharse para hacer que documentos de texto como documentaciones se vean mejor con muy poco esfuerzo, e incluso se pueden crear páginas web en conjunto con otras herramientas.

Los archivos de Markdown usan la extensión `.md`

**Nota**: Los lenguajes de marcado como Markdown y HTML no son lenguajes de programación.

**Nota 2**: Este material está escritos en Markdown.

## Texto
En Markdown se puede modificar la apariencia de un texto de estas formas.

\*\*Negrita\*\*: **Negrita**

\*Itálica\* o \_Itálica\_ :  *Itálica*

\<u>Subrayado\</u>: <u>Subrayado</u>

\~\~Tachado\~\~ : ~~Tachado~~

**Headings**

Los headings o títulos se marcan añadiendo el caracter '#' al principio de una línea.

El tamaño de un header varía según cuántos '#' se usen. Pueden usarse de 1 a 6, siendo 1 el más grande y 6 el más pequeño.

\# Título 1

\### Título 2

\###### Título 3

# Título 1

### Título 2

###### Título 3

## Line breaks

Los line breaks, espacios o saltos de línea se pueden hacer insertando dos pulsaciones de la tecla enter.

Lo siguiente son dos línea de texto:

```
hola
mundo
```
Pero en markdown esto se renderiza en una sóla línea como `holamundo`.

En cambio si dejamos una línea vacía entre ambas, esto es interpretado como dos párrafos distintos.

```
hola

mundo
```

Queda como:

hola

mundo

## Listas

Markdown admite la creación de listas ordenadas y no ordenadas.

\- Elemento de lista no ordenada

\- Elemento 2

- Elemento de lista no ordenada
- Elemento 2

\1. Elemento de lista ordenada

\2. Elemento 2

1. Elemento de lista ordenada
2. Elemento 2

## Bloques de código

Para añadir bloques de código se usan los backticks (\`).

\`Bloque in-line\`: `Bloque in-line`

Este bloque sólo es de una línea. Para hacer bloques multilínea se usan tres backticks.

\`\`\`python

import sys

sys.out.write("Hello world\n")

\`\`\`

En este ejemplo añadimos un bloque multilínea con código Python. Tras los primeros 3 backticks podemos (no es obligatorio) poner el lenguaje del código que incluiremos. Hacer esto puede habilitar el resaltado sintáctico del código con colores. El código va debajo de los primeros tres backticks.

```python
import sys
sys.out.write("Hello world\n")
```

## Citas

Un bloque de cita in-line se hace con el caracter '>'

\> Esto es una cita.

> Esto es una cita.

En algunos intérpretes de Markdown, esta forma de citar es multi-línea también, y se cierra colocando 2 saltos de línea (2 pulsaciones de tecla enter).

Se pueden incluso hacer citas anidadas.

\> Cita

\>\> Cita anidada 1

\>\>\> Cita anidada 2

\>  Cita 2

> Cita
>> Cita anidada 1
>>> Cita anidada 2
> Cita 2

## Enlaces y multimedia

Para añadir enlaces en Markdown se puede seguir la siguiente sintaxis: `[Texto](URL)`

Por ejemplo: `[Ir a Google](https://google.com)`

Queda así: [Ir a Google](https://google.com)

Si quisiéramos añadir un enlace sin ningún texto lo ponemos entre \< >.

Ejemplo: `<https://google.com>`

Queda así: <https://google.com>

Para añadir imágenes la sintaxis es similar:

`![texto alternativo](URL o ruta)`

Donde el "texto alternativo" es lo que se mostrará si por algún motivo el parser no puede mostrar la imágen. Y en los paréntesis pones una URL si tu imágen está en internet o la ruta de la imagen si tu imagen está en el servidor donde está siendo hosteada la web o donde está siendo abierto el documento.

Esto:

```
![](https://live.staticflickr.com/2193/2216904775_96a3063b35_c.jpg)`
```

Produce esto:

![](https://live.staticflickr.com/2193/2216904775_96a3063b35_c.jpg)

## Escapes

En Markdown si queremos escribir caracteres que representan una función del lenguaje pero queremos que el parser lo ignore, usamos el caracter de barra invertida (\\) antes de dichos caracteres.

Por ejemplo, para escribir \*Hola\* sin que el parser formatee el texto en itálica hay que poner barras invertidas así: \\\*Hola\\\*.

A esto se lo llama **escapar un caracter**. Porque hacemos que el caracter escape de ser parseado y pasa a ser ignorado.

## Tablas

Las tablas se pueden hacer de una forma muy intuitiva.

Este ejemplo lo demuestra:
```markdown
Nombre|Edad
---|---
ABC|21
DEF|18
```

Y eso da este resultado:

Nombre|Edad
---|---
ABC|21
DEF|18

## Misceláneo

Para dividir contenidos se puede añadir una barra horizontal añadiendo tres guiones o tres asteriscos.

Así `---` genera esta barra:

---

Pero si se usa la forma de los tres guiones se debe dejar una línea vacía previa a la barra horizontal, de lo contrario será interpretado como un heading y no saldrá la barra.

Finalmente, Markdown admite la inserción de etiquetas HTML.

```HMTL
<p style="color:blue">¡Fin del documento!</p>
```

<p style="color:cyan;font-size:25px">¡Fin del documento!</p>

