# Reporte: Comandos con gitbash

## Navegando en la terminal de gitbash:

### 1. Navegando en el directorio con gitbash  
Dentro de la terminal de git bash, en el siguiente codigo estamos navegando entre los folders del directorio, tambien al final de este, inicializamos un repositorio vacio local.
``` bash
cd .. #regresas una carpeta arriba
cd . 
pwd #saber el directorio actual.

ls -a #muestra archivos ocultos
ls -l #lo muestra mas bonito

$git init #crear repositorio local, master.

mkdir nombrefolder
```

### Captura de pantalla:
![NavegandoTerminalBash](/imagenes/navegandoTerminalGit.png)

#### pie de foto: aqui mediante los comandos de `cd` y `ls` navegamos entre directorios y despues de encontrar la carpeta en la que deseamos crear un directorio, procedemos a desde esta, utilizar el comando `git init`.
---
### 2. Realizar cambios desde la terminal, **git bash**

Por ejemplo, pudimos observar en la anterior captura de pantalla que utilizamos el comando `touch` seguido de un nombre. En este caso debe terminar en `.md` no -md. Fue mi error y ha sido corregido. 

``` bash
touch //puedes crear un archivo, debes de escribir el nombre y su extension, ejemplo:
touch README.md // se creara un archivo llamado README que sera de markdown.

```
**Continuando donde lo dejamos, para modificar un archivo desde la terminal**, se debe escribir el siguiente comando `nano {nombre-de-tu-archivo}` (reemplazando las llavees y su contenido por el nombre de tu archivo).

### [EJEMPLO] Captura de pantalla, una vez ejecutado `nano README.md`:
![EditorEnTerminal](/imagenes/editorenterminal.png)

#### Lo que sucede es que nos abre este menu dentro del gitbash donde, primero que nada, nos aparece el contenido del archivo que hayamos creado, en este caso yo tenia la informacion en amarillo y en la parte de abajo tenemos un directorio de opciones.  
Este comando es util en caso de que queramos realizar cambios muy minimos sin la necesida de entrar en un IDE, como vscode, entre otros. En la parte de abajo, podemos encontrar algunos comandos, para salir de este modo y regresar a la terminal debemos de realizar la combinacion `CTRL+Z`.

**Otro datos:**
* Puedes abrir tu IDE de preferencia unicamente usando la consola con la combinacion `code {nombre-de-tu-archivo}` 
* Con la combinacion `cat {nombre-de-tu-archivo}`, se abrira directamente en la terminal el contenido que tenga ese archivo, ya sea codigo o escritos.
* ejemplo:
![ComandoCat](/imagenes/comandocat.png)
---
### 3. Subir repositorio a GitHub

Para subir nuestra repo local a github, debemos de realizar lo siguiente:

``` bash
$git init # Si no lo haz hecho, este comando es para iniciar un repositorio local
$git add # agregar cualquier documento o un documento en especifico para subirlo a github.
$git commit -m {agrega-comentarios-de-tus-commits-queson-paraqueson} # aqui una vez que estes segura de lo que deseas subir, debes de confirmarlo haciendo un commit y agregando un mensaje descriptivo del commit.
```
![commits](/imagenes/commits.png)

> Esto no se reflejara en tu github porque todavia no has enlazado un repositorio de este con tu repositorio local.
---
### 4. Como enlazar un repositorio en GitHub a un repositorio local.

Primero que nada, hemos realizado el metodo con la contraseña SSH (Secure Shell Protocol). 

*Para crearla debes de introducir este comando en gitbash:
`ssh-keygen`* Y despues en determinadas instrucciones debes de darle solo a la tecla ENTER.
![SSH-Keys](/imagenes/ssh.png)
> Este archivo se introducira al momento de habilitar el medio de ssh en github.
---
**Este al momento de crear un repositorio en github,** no incluiremos el readme y agregaremos un titulo y descripcion del repositorio. \
Ahora ya teniendo configurado todo del SSH, procedemos a copiar el enlace que nos sale en `code/clone` y lo pegaremos en la terminal donde deseamos enlazar ese repositorio.

``` bash
$git remote add origin git@github.com:andreagori/ParadigmasProgramacion.git #url del repo en linea
$git push -u origin <branch> #(master, main, entre esas).

```
### Esta es la respuesta de lo que saldria en la consola: 
![reposOnline](/imagenes/subiendorepos.png)
#### Y asi seria tener tu repositorio local ahora en linea y enlazarlo.
---
### 5. Crear ramas diferentes en un repositorio

Clonar un repositorio local con un nombre distinto sin alterar el contenido original
``` bash
# CAMBIAR EL NOMBRE DE LA CARPETA DEL GIT CLONE SIN ALTERAR EL CONTENIDO
$git clone git@github.com:andreagori/ParadigmasProgramacion.git <ingresaelnombredelacarpetaquequieras>
```

Para **manejar o crear ramas** se utilizan estos comandos, pero si deseas obtener la documentacion sobre estos, puedes escribir lo siguiente en tu terminal de git bash:

``` bash
# CREAR UN NUEVO BRANCH, AYUDA
$git branch --help 

# EL COMANDO CHECK UP, ES EL QUE SE USA MAS. 
$git checkout --help 
```
El comando que usaremos mas o el mas utilizado, es el ***checkout***.
![ramitas-help](/imagenes/checkout.png)

``` bash
# Para crear una nueva rama, debes de estar en un repositorio local
$git checkout -b <ingresaelnombredetunuevarama> 

# Para abrir desde la terminal vscode 
$ code readme.md 

# De nuevo, como se actualiza la rama y revisar cambios.
$git add <nombredearchivoOsimplementepunto>
$git commit -m "mensaje del commit, breve descripcion de lo que hiciste"
$git status

# Subir los cambios de la branch rama via remota 
$git push -u origin <nombredelaramaquecree>

```
![ramitas-github](/imagenes/ramitagithub.png)
#### aqui podemos ver los cambios reflejados en github despues de realizar el psuh, y como tenemos dos ramas, la master que es la original y "rama" que es la que hicimos.

Al entrar en la nueva rama, deberiamos de ver los cambios realizados en el README.md

![ramita-github](/imagenes/contenidoRama.png)
![github-grafica](/imagenes/grafica.png)

---
Nosotros en clase, realizamos este proceso mas veces para observar el cambio en la grafica de red respecto a las ramas, aqui esta como se veria:
![grafica-avanzada](/imagenes/ramitas.png)
---
### Comandos EXTRAS realizados:
``` bash
# SI HICISTE UN CAMBIO EN CODIGO Y NO LO QUIERES AGREGAR, AL DARLE GIT STATUS APARECE
# PERO DESPUES HAREMOS ESTO
$git restore <nombredelarchivo> 
# ELIMINARA LA LINEA DE CODIGO QUE TENIAS EN VSCODE.
```

``` bash
# MOSTRARA TODOS LOS CAMBIOS REALIZADOS EN LOS ARCHIVOS
$git diff 
```

``` bash
# SI LE DI A ADD, CUANDO NO QUERIA AGREGARLO, COMO REGRESARLO: 
$git restore --staged <nombredelarchivoagregado> 
```

![comandos](/imagenes/extrascomandos.png)

# FIN PRACTICA MARKDOWN.