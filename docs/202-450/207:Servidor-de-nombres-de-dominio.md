# Tema 105: Shells y scripts

[BASH (Bourne-again shell](https://es.wikipedia.org/wiki/Bash)) - es un programa escrito en C que interpreta las ordenes escritas por consola para interactuar con el sistema. [Manual](https://www.gnu.org/software/bash/manual/)

## 105.1 Personalizar y usar el entorno de shell

### Setting Up the Shell Environment

Tenemos que tener en cuenta que hay varios tipos de consolas:

- **Consolas interactivas de acceso**. (Interactives Login Shell).

  - Es la consola que se crea cuando te logas en una ventana de terminal sin escritorio.
  - Consola que se crea cuando nos logamos por SSH.

- **Consola interactiva sin acceso**. (Non-login terminal)
- Es una consola creada por otra aplicación, por ejemplo la terminal que abrimos desde un entorno de escritorio en GNOME.

> Si hacemos un echo \$0 sobre la terminal podemos saber que tipo de consola es

Login Shell: `bash`
Non-Login Shell: `-bash`

> La diferencia esta en el carácter "-"

**Archivos**

`/etc/profile` - es el primero fichero que se lee cuando se accede a una nueva sesión. Configura las variables de entorno que serán usadas por esta consola, como valore de umask, historial de bash, etc.

`/etc/profile.d/` - directorio que contiene scripts de configuración extra para bash.

`/etc/bashrc` - fichero de configuración de funciones y alias.

`/etc/skel` - es el directorio que contiene la plantillas que se aplican cuando se crea un usuario nuevo.

Para modificar los alias y las funciones de un usuario tendremos que modificar el fichero `~/.bashrc`.

### Customizing the Shell Environment

`env` - nos muestra todas las variables de entorno configuradas para la shell actual.

`export` - comando para exportar una variable de entorno para la bash actual y las bash que se creen por debajo de ella.

`set` - nos muestra la configuración de todas las consolas bash, variables y funciones. Puede ser utilizado para habilitar y deshabilitar configuraciones de la bash.

Por ejemplo si queremos deshabilitar el file globing `set -f` . Para volver habilitar usamos `set +f`.

`unset` - se utiliza para borrar una variable de entorno.

`Alias` - los alias son acceso directos a comandos y se añaden en el fichero bashrc.

`function` - las funciones son una serie de ordenes que se ejecutan cuando la función es llamada. Es útil para tareas repetitivas.

En caso de que cambiemos o añadamos algún **alias** el fichero de **bashrc**, tenemos que pararle la opcion `source` para que se actualice.

```s
source ~/.bashrc
```

`PATH` - es la variable de entorno que contiene los directorios que la bash utilizara para poder ejectuar un programa sin tener que especificar la ruta completa. Es una variable muy importate.

## 105.2 Personalización y escritura de scripts sencillos

Los scripts son una colección de comandos que hacen alguna acción concreta.

Los scripts se identifican por el tipo de consola en la que se ejecutan.

Indicamos que el script lo va a ejecutar la shell de **bash**.

```s
#!/bin/bash
```

Se pueden pasar parametos a la ejecución de scripts definiendolos así -> `$1` parametro 1, por ejemplo `./myscript.sh text.txt` lanzará el script tomando como valor `$1` `text.txt`.

### Basic Shell Scripts

```s
#!/bin/bash
# Crea un fichero vacio y añade contenido a el
touch $1
echo "Esto es un fichero de prueba" > $1
#Lanzo un clear para limpiar la pantalla y muestro el fichero
clear
cat $1
```

**¿Dónde están ubicados los script del sistema?**

- `/usr/bin` - script del sistema
- `/usr/local/bin/` - scripts instalados o creados por los usuarios para ser utilizados en el sistema local.
- `/home/user/bin` - scripts creados por el usuario y solo disponibles para el usuarios.

### Bash Loops and Sequences

- `for`
- `while`
- `until`

Ejemplos [aquí](https://es.wikibooks.org/wiki/El_Manual_de_BASH_Scripting_B%C3%A1sico_para_Principiantes)

---

`read` Leemos lo que introducimos por teclado y lo guardamos en la variable GRETTING. `read GREETING`.

`exit` - para especificar el retorno de salida, normalmente seria 0, pero se puede cambiar a otro numero, por ejemplo para salir en un bucle.

`exec` - se puede utilizar para re-direccionar la salida de una shell a un fichero. `exec > out .log`

---
