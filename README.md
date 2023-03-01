# Curso de _Git_ & _GitHub_

Empezando con Git y GitHub

## Flujo basico

### Working Directory

Consiste en los cambios locales y que git aun no los ha visto.

Ojo: Puedo pasar de remote a working directory por medio del comando git pull. Con este obtengo los cambios que se hayan hecho en el remoto y comienzo a seguir con mi parte. 

Comando: git pull

### Index/Staging

Consiste en cambios que git ya los ha notado, mas sin embargo no los ha guardado en el historia.

comando: git add

### Head/Local

Consiste en los cambios que git ha realizado en el historial.

comando: git commit

### Github/Remote

Consiste en los cambios que se encuentran en el directorio remoto

comando: git push

## Master a Main

Pasamos de Master a Main por un tema social y politico. No es un tema de programación. 

### Pasando de master a main

#### Repositorios existentes

Primero creamos la rama main con git branch -m master main

Luego cambiamos el push -u originb. git push -u origin main

Luego cambiamos el flujo del head, la tercera etapa. git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main

Luego vamos a github y en configuracion de branches cambiamos de master a main.

Por ultimo podriamos eliminar la rama master con un git push origin --delete master

#### Repositorios nuevos

simplemente hacemos lo siguiente

git init
git add .
git branch -m main
git remote add origin ruta
git commit -m ""
git push -u origin main