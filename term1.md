Dificultad: **Fácil-intermedio**

Tiempo estimado para aprenderlo: **20-25 mins**

## Tabla de contenidos
- [Introducción](#introducción)
- [Breve historia de la terminal](#breve-historia-de-la-terminal)
## Introducción

Ua terminal es más que "una pantalla negra con letritas verdes que usan los hackers en las películas", por eso, en este capítulo se definirá lo que es introduciendo sencillamente conceptos nuevos.

**Conceptos necesarios para entender:**
- [Diferencia entre sistema operativo y kernel](sys1.html)

Se llama terminal a un conjunto determinado de elementos que funcionan juntos, y de ellos los que vamos a destacar son: **emulador de terminal y shell** (consola).

## Breve historia de la terminal

*Esta parte es obligatoria para entender correctamente*. 

Antiguamente se llamaba terminal, a los **teletipos**, comúnmente abreviados **TTY** por *"teletype"*. En ese tiempo las computadoras eran bastante grandes, esas computadoras son **mainframes**, o unidades centrales, que se encargaban de procesar los programas que les introducían.

La primera opción de interacción en tiempo real entre el ser humano y las computadoras fue gracias a la creación de los teletipos. Estos eran dispositivos que contenían un teclado y un rollo de papel. Los teletipos sólo habilitaban la interacción con las computadoras, pero no tenían ningún tipo de capacidad de procesamiento, en cambio, iban conectadas a los **mainframes** para poder interactuar con ellos. Incluso se podían conectar varias TTY, haciendo que varios usuarios usen la misma computadora.

No había mouse entonces porque tampoco habían programas gráficos, sólo se interactuaba con comandos de terminal, y para eso estaba el teclado; y en lugar de haber pantalla, los resultados de los comandos se imprimían en el rollo de papel

![img](https://upload.wikimedia.org/wikipedia/commons/thumb/d/df/ASR-33_at_CHM.agr.jpg/440px-ASR-33_at_CHM.agr.jpg)

![img](https://i.ytimg.com/vi/2XLZ4Z8LpEE/maxresdefault.jpg)

Luego las TTY evolucionaron para incluir una pantalla digital, siendo el modelo VT-100 la primera TTY física con esta característica.

![img](https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/DEC_VT100_terminal.jpg/1200px-DEC_VT100_terminal.jpg)

Esta foto es la TTY VT-100, pero de nuevo, esto no es una computadora, esta TTY iba conectada a una computadora central por conexión serial para poder usar la computadora a través de esa TTY.

Y finalmente hoy en día todo el sistema de TTY va incluido dentro de nuestras computadoras, con componentes y programas que emulan el comportamiento de las TTYs físicas.
## Emulador de terminal

Un emulador de terminal es un programa que emula el funcionamiento de una TTY física. Este se encarga de leer la entrada del teclado y enviarla al proceso correspondiente, y se encarga también de redireccionar la salida de los programas hacia la pantalla.

Ejemplos de emuladores de terminal son el emulador de TTY virtual incluida en el kernel Linux, el programa cmd.exe en Windows, la aplicación Termux en Android, y otros programas como Alacritty y Kitty que también son emuladores de terminal.

En la descripción no se dijo que estos programas lean comandos, y eso es porque no lo hacen. Al iniciar una sesión de terminal estos programas suelen invocar una shell (consola), que se encargue de eso.

## Shell

Una shell o consola, es un programa que se encarga de interpretar comandos de terminal.

Ejemplos de shell son: bash, que viene por defecto en casi todas las distros GNU/Linux; la shell de cmd o powershell en Windows, zsh en MacOS, etc.

![img](https://miro.medium.com/v2/resize:fit:1400/1*GugKOJXJTFqpag3HwtdsJw.jpeg)

## Definición de comando

Un comando puede ser de 2 tipos: puede ser una instrucción reconocida por una shell, o puede ser un programa instalado en el sistema.

Por ejemplo, usando la shell **bash** como ejemplo, el comando `cd` que sirve para moverse entre directorios, es una instrucción reconocida por la shell, y por ende decimos que este comando es un **comando built-in**, porque es parte del código de la shell.

Pero luego otros comandos como `ls` *(que sirve para listar los archivos en un directorio)*, o `apt` *(que en sistemas basados en Debian sirve para administrar paquetes)* son programas. En instalaciones GNU/Linux estos suelen estar instalados en el directorio  `/usr/bin/`.

Cuando se intenta ejecutar un comando en bash, por ejemplo, la shell intentará chequear la existencia del comando en el siguiente órden
1. Alias o función
2. Built-in
3. Programa

**Nota**: Un alias es un nombre designado por el usuario para referenciar otro comando.

Entonces, si usamos el comando `apt`, bash chequeará si es un alias y fallará, luego buscará si es uno de los comandos built-in y fallará, entonces luego procederá a buscar dentro de las rutas de archivos especificadas en la variable de entorno `$PATH`; puedes pensar en esto último como una configuración de la shell que le dice a bash en donde están almacenados todos los binarios de programas instalados. Entonces bash finalmente buscará entre las rutas en `$PATH` para finalmente encontrar este programa en `/usr/bin/apt`.

