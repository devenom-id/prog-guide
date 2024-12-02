Dificultad: **Fácil**

Tiempo estimado para aprenderlo: **20 minutos**

## Índice
- [Instalar paquetes](#instalar-paquetes)
- [Actualizar bases de datos de apt](#actualizar-bases-de-datos-de-apt)
- [Actualizar paquetes](#actualizar-paquetes)
- [Remover paquetes](#remover-paquetes)
- [Listar paquetes](#listar-paquetes)
- [Buscar paquetes](#buscar-paquetes)
- [Información sobre un paquete](#información-sobre-un-paquete)

---

En Debian y los sistemas derivados, el gestor de paquetes es `apt`. `apt` es capaz de realizar todos los trabajos de gestión de paquetes.

**SINTAXIS**

```
apt [operación] [opciones] [paquete]
```

Cada operación de `apt` tiene distintas opciones, estas suelen tener dos versiones sinónimas, una versión corta y una extendida, por ejemplo, la versión extendida de la opción `-d` de la operación install es `--download-only`.

## Instalar paquetes

Para esto se utiliza la operación install seguido del nombre del paquete, esto se hace de la siguiente forma:

```
apt install [paquete]
```

`[paquete]` debe ser reemplazado por el nombre del paquete que se desea instalar. Para las instalaciones se requiere que el usuario tenga permisos elevados tendrá que preceder `apt` con el comando `sudo` pasando `apt` como argumento de `sudo`. Lo anterior debe ser así:

```
sudo apt install [paquete]
```

Para instalar paquetes localmente sólo debes poner la ruta del paquete.

```
Ejemplo: sudo apt install [/ruta/hacia/paquete.deb]
```

## Actualizar bases de datos de apt

Para actualizar la base de datos de los repositorios de Debian y derivadas, se usa la operación `update`:

```
apt update
```

Es recomendable utilizarlo durante la primera ejecución de una distribución Debian o basada en Debian, de igual forma se recomienda su uso tras cierto tiempo, ya que algunos paquetes podrían tener versiones nuevas, cambiar de nombre o ser eliminados/reemplazados. Para usar esta operación se necesitan privilegios de superusuario, por ende, se debe preceder `apt` con `sudo`.

## Actualizar paquetes

Regularmente se deben actualizar los paquetes, esto es necesario para tener todos los programas en sus versiones más recientes, los últimos parches de seguridad y la última versión del kernel. Esto no sólo es para tener las mejores versiones de los programas, sino para tener un sistema más seguro.

Hay dos operaciones que se usan para actualizar los paquetes.

```
sudo apt upgrade
sudo apt full-upgrade
```

La diferencia entre ambas es que `upgrade` actualiza todos los paquetes que tienen actualizaciones disponibles excepto por aquellos que requieren la desinstalación de otro paquete para su actualización, en cambio `full-upgrade` ejecutará todas las acciones necesarias para actualizar completamente el sistema.

Es recomendable usar `apt update` antes de hacer un `upgrade` o `full-upgrade`.

## Remover paquetes

Para remover paquetes hay tres operaciones, estas son:

```
sudo apt remove [paquete]
sudo apt autoremove [paquete]
sudo apt purge [paquete]
```

Si se desea simplemente remover un paquete, se usa la operación `remove`. Si se busca eliminar un paquete y sus dependencias, se usa `autoremove`, esta operación sólo eliminará los programas o librerías que sólo sean dependencia del programa que se busca eliminar, sino se mantendrán.

Si lo que se busca es eliminar un paquete y sus archivos de configuración, se usa la operación `purge`. (Tenga en cuenta que purge no eliminará configuraciones que se guarden dentro de `/home/$USER`)

## Listar paquetes

Para listar paquetes se usa la operación `list`. Si se desean listar todos los paquetes disponibles, se usa:

```
apt list
```

Si lo que se busca es listar sólo los instalados, se pasa la opción `--installed`.

```
apt list --installed
```

Para listar los paquetes que tengan actualizaciones disponibles, se usa la opción `--upgradeable`.

```
apt list --upgradable
```

## Buscar paquetes

Si se quiere buscar un paquete entre la lista de los paquetes disponibles se usa la operación `search`.

```
apt search [paquete]
```

## Información sobre un paquete

Para obtener una descripción sobre un paquete se usa show.

```
apt show [paquete]
```
