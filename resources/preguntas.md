# Ejercicio 1
Capacitación: Git, bash y docker
Integrantes:
- Andrés Muñoz 
- Deisy Sapaico
- Pedro Pairazaman

1. ¿Qué es y para qué sirve GIT?

Git es un sistema de versionamiento que sirve para registrar cambios en un repositorio.

2. ¿Que es Github o bitbucket?

Plataformas donde se alojan repositorios de Git permitiendo la colaboración entre personas.

3. ¿Qué es y para qué sirve el SSH?

Es un protocolo que permite la comunicación entre una maquina local con un servidor de git.

---

4. ¿Que pasa si cambio de PC? ¿Tendré que generar el SSH nuevamente?¿Por qué?

Si, porque las llaves de comunicación son únicas y deberian  ser personales.

5. ¿Qué es markdown? ¿Para qué sirve?

En un lenguaje de marcado que sirve para dar formato a textos. su extensión es .md

6. ¿Cómo inicializo y configuro un proyecto de git?

Se inicia creando  un repositorio con el comando:

```
$ git init. 
```

Luego agregamos el nexo por defecto llamado **origin**: 

```
 git remote add origin [Ruta-repositorio-remoto]
```

Debemos tener en cuenta registrar nuestro usuario y correo en la configuración global de git con los  siguientes comandos:

```
$ git config --global user.email "you@example.com"
$ git config --global user.name "Your Name"
```

#Parte 4

1. ¿Que importancia tienen los tags en un proyecto?
Ayudan a versionar proyectos


2. ¿Cual es la diferencia entre un tag normal y un tag anotado en git?
En un tag normal solo indicamos la versión. En un tag anotado colocamos un mensaje asociado al tag.

3. ¿Cómo se sube todos los tags de git que hay en mi local?
Los cambios se suben con comando: git push origin --tags


4. ¿Es necesario loguearse cada vez que subo una imagen a dockerhub?
No, con loguearse una vez basta. Sin embargo se debe estar logueado para subir una imagen la primera vez.

5. ¿Qué es y para que sirve docker?
Docker es una plataforma  que permite desarrollar , implementar y ejecutar aplicaciones dentro de contenedores.

6. ¿Cual es la diferencia entre docker y VirtualBox ?
Docker usa las caracteristicas del kernel de un sistema operativo para ejecutar contenedores. Vitualbox usa los recursos del hardware de la maquina en que nos encontremos.

7. ¿Es necesario depender de una imagen de docker base al crear una imagen nueva?
Generalmente si. Sin embargo, puedo crear una imagen desde cero, sin tener una imagen base.

8. ¿Por que debo anteponer el nombre de usuario en una imagen de docker nueva?
Por que de esa manera docker reconoce mi usuario de docker y sabe a repositorio debe ser subido.

9. ¿Que pasa si creo una imagen sin especificar una version o tag, con que version se crea?
Se crea con el tag 'latest'

# Parte 5

1.1 ¿Porqué es necesario crear un contenedor con esta bandera -it?

Para poder interactuar (visualizando la ejecuciòn en consola) con la copia de la imagen docker(contenedor) 


1.2 ¿Qué pasa si no le pongo -it?

Si no ponemos -it, el contenedor se crea en un proceso por debajo (background) y no me permitiria acceder al contenedor 

1.3 ¿Para qué sirve ejecutar el comando bash al 
ejecutar una imagen?

Sirve para acceder al contenedor mediante el la interface de bash

2.1  ¿Cuál es la diferencia entre docker ps y docker ps -a?

Con **docker ps** vemos los contenedores activos y con **docker ps -a** visualizamos los contenedores con cualquier estado.

3.1 Agregar el comando para ejecutar el contenedor

docker exec -it idContenedor bash


5.1. ¿Cuál es la diferencia entre una imagen y un contenedor?
Una imagen es una especie de plantilla. Un contenedor es una instancia a traves de la cual voi a acceder a una imagen

2. ¿Cómo listo las imágenes que hay en mi computadora?
ls

3. ¿Cómo salgo de un contenedor de docker?
exit

4. ¿Se elimina el contenedor al salir de ella?
NO
5. ¿Cómo elimino un contenedor?
docker rm idContenedor

6. ¿Para qué es necesario el flag `-i`, `-t`, `--rm`?
-i : permite interactuar con el contenedor una vez creado
-t : permite indicar que la interface sea por defecto (terminal)
--rm: remueve el contenedor una vez se haya detenido

7. ¿Cómo verifico que el archivo creado se encuentra en la imagen?

creo un contenedor : docker run -ti
listo ls directorios : ls
Verifico el archivo: cat rutaDelArchivo

8. ¿Cómo se comenta una linea de código en Dockerfile?
Es iniciando la línea con el símbolo **#**


Parte 8. paso 5

1. ¿Qué es bash? ¿Qué significa?
Es un programa que ejecuta comandos.  Sus siglas significan 'Bourne-again shell'

2. ¿Cómo ejecuto un archivo bash?
Especificando en la primera linea **#!/bin/sh**, luego ejecuto el archivo con el comando: **./[mi_script]**

3. ¿Qué pasa si no especifico en un `.sh`, la linea `#!/bin/bash`?
El sistema por defecto lo considera al script como un archivo bash, incluso sin necesidad
de especificar la extensión **.sh**

4. ¿Se puede cambiar el modo bash (`/bin/bash`) a otro tipo de ejecución?
Si, por ejemplo para ejecutar el archivo con **python**

5. ¿Cómo se envía variables de entorno por Docker CLI y docker-compose?
Por docker CLI, enviamos una variable de entorno con el comando -e nombreVariableEntorno="valor".  Por docker-compose se define la variable en el archivo .yml con la sgte sintaxis:

```
     environment:
      - nombre="xD"
```
Parte 9. paso 8

1. ¿Para qué sirve el archivo `Makefile`?
Sirve para definir comandos qe contienen instucciones personalizadas, que pueden ser ejecutados mediante un interprete de linea de comandos

2. ¿Qué es un `target` en `Makefile`?
Un target permite definir uno o varios comandos, en una sola instrucción

Parte 10. Paso 7

1. ¿Qué significa el comando -d?
El comando -d indica la existencia de un directorio. Como ejemplo temnemos lo ejecutado en la instrucción " @if [ ! -d "$(GIT_BRANCH_DIR)" ]; then mkdir $(GIT_BRANCH_DIR); fi" 

2. ¿Porqué la sentencia comienza con @?
Porque de esta manera le decimos que el comando que prosigue luego de '@' no se muestre en el comando de la ejecución en consola.


3. ¿Para qué sirve el comando mkdir?
Sirva para crear un directorio. Ej. mkdir nuevodir


4. Explicar lo que hace la función mkdir_deploy_dir
La funcion 'mkdir_deploy_dir' verifica: si no existe la ruta "/ORBIS-TRAINING-PROJECT/deploy/gh-pages" entonces procederá  a crear dicha carpeta en la ruta.

```
define mkdir_deploy_dir
    @if [ ! -d "$(GIT_BRANCH_DIR)" ]; then mkdir $(GIT_BRANCH_DIR); fi
endef
```

Parte 10. Paso 8

1. ¿Para qué sirve el uso de \?
Sirve para poder ordenar las instrucciones una debajo de otra, en el archivo makefile

```
define git_init
    @cd $(GIT_BRANCH_DIR) && \
     rm -rf $(GIT_BRANCH_DIR)/.git && \
     git init
endef
```

2. ¿Para qué sirve el uso de &&?
 "&&" significa "and" . Sirve para unir dos o más instrucciones en un solo comando


3. ¿Qué función cumple usar los argumentos -rf?
Significa "remove folder", lo cual indica que se va aeliminar una carpeta


4. Explicar lo que hace la función git_init (linea por linea)
@cd $(GIT_BRANCH_DIR) && \  -> Ir a la ruta /ORBIS-TRAINING-PROJECT/deploy/gh-pages
rm -rf $(GIT_BRANCH_DIR)/.git && \  -> Eliminar el directorio ".git"
 git init  ->  Inicializar el proyecto en git creando una nueva carpeta .git


Parte 10. Paso 9
```
define git_config
    $(eval GIT_USER_NAME := $(shell git log --pretty=format:"%an" | head -n 1))
    $(eval GIT_USER_EMAIL := $(shell git log --pretty=format:"%ae" | head -n 1))
    @cd $(GIT_BRANCH_DIR) && \
     git config user.email "$(GIT_USER_EMAIL)" && \
     git config user.name "$(GIT_USER_NAME)"
endef
```

1. ¿Para qué sirve el uso de eval?
Permite evaluar si la variable está o no definida. Si no lo está, se procede a indicar su definición


2. ¿Para qué sirve el uso de shell?
Sirva para indicar que las instrucciones seguidas de "shell" son instrucciones a ejecutar en el interprete de comandos shell


3. ¿Para qué sirve el uso de git log --pretty=format:"%an"?
git log -> Muestra una bitácora del repositorio a nivel local en la rama en la que se encuentra actualmente.
--pretty=format:"%an"  -> Muestra los nombres de los autores de los commits que se encuentran en la bitácora

4. ¿Cuál es la diferencia en usar git config y git config --global?
git config, permite cambiar  el valor de las variables de entorno en el repositorio en el cual estamos situados
 git config --global, permite cambiar  el valor de las variables de entorno en todos los repositorios de mi pc

```
git config --global user.email "pedro_pps@hotmail.com"
```

5. Explicar lo que hace la función git_config (línea por línea)

    $(eval GIT_USER_NAME := $(shell git log --pretty=format:"%an" | head -n 1))  -> Se indica el valor que tendrá la variable "GIT_USER_NAME". tomandola del log(lista todos los usuarios de la bitácora y muestra el ultimo que realizó cambios)
    $(eval GIT_USER_EMAIL := $(shell git log --pretty=format:"%ae" | head -n 1))  -> Se indica el valor que tendrá la variable "GIT_USER_EMAIL". tomandola del log(lista todos los emails de usuarios de la bitácora y muestra el ultimo que realizó cambios)
    @cd $(GIT_BRANCH_DIR) && \  -> Nos situqmos en la ruta /ORBIS-TRAINING-PROJECT/deploy/gh-pages
     git config user.email "$(GIT_USER_EMAIL)" && \  -> En el repositorio "/ORBIS-TRAINING-PROJECT/deploy/gh-pages" asignamos un valor a la variable "user.email" 
     git config user.name "$(GIT_USER_NAME)" ->  En el repositorio "/ORBIS-TRAINING-PROJECT/deploy/gh-pages" asignamos un valor a la variable "user.name" 

Parte 10. Paso 10

    ¿Para qué sirve el uso de awk?
    ¿Para qué sirve el uso de sed?
    ¿Para qué sirve el uso de git log --pretty=format:"%an"?
    Explicar lo que hace la función git_add_remote_repository
