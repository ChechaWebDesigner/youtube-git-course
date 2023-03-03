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

## Ignorando archivos

Para ignorar archivos es como usar expresiones regulares

El # me sirve para comentarios

*.txt Todos los archivos txt

doc/*.txt Todos los archivos txt dentro de doc

doc/**/\*.txt Todos los archivos txt que esten en cualquier subcarpeta de doc

!yoNo.txt Este .txt no lo elimino, es decir si lo subo.

## Clonar

Es clonar otro repositorio. Basicamente una copia identica.

comando: git clone url.

## Ramas

Es una nueva funcionalidad que añadimos luego a la version principal

Los archivos que creó en otra rama, unicamente aparecerán dentro de la otra rama. Osea si creo una rama a y dentro de ella creo un componente. Dicho componente no aparecerá dentro de la rama main o de las otras. Eso si, la rama en donde creo la otra, tomará como base la rama desde la cual se creó. 

### crear rama
git branch nombre-rama

### cambiar de rama
git checkout nombre-rama

### crear una rama y cambiarte a ella
git checkout -b rama

### eliminar rama
git branch -d nombre-rama

### eliminar ramas remotas
git push origin --delete nombre-rama

#eliminar rama (forzado)
git branch -D nombre-rama

### listar todas las ramas del repositorio
git branch

Basicamente es ver todas las ramas. Tipo un dir o lr en la terminal, pero con git y sus ramas.

### lista ramas no fusionadas a la rama actual
git branch --no-merged

### lista ramas fusionadas a la rama actual
git branch --merged

### rebasar ramas
git checkout rama-secundaria
git rebase rama-principal

## Status

Me permite ver en que estado se encuentran los documetos. Si estan modificados, en stage, en commit.

comando: git status 
comando preferido: git status -s

## ¿De donde viene el -u?

El -u proviene de la abreviación del comando --set upstream 

## Fusionar

Es cuando obtenemos una union entre dos ramas. 

Hay dos tipos:

1. Fast-Forward: Las que son automaticas y en ellas no hay conflictos.

2. Manual Merge: Son manuales y en ellas hay conflictos. Ya que cambiamos el mismo archivo en dos ramas y no saben con que contenido quedarse.

comando: git merge rama externa

Ojo: Debo estar en la rama actual, es decir la que quiero que jale la info de la otra rama. 

### Eliminar rama virtual

comando: git push origin --delete name

## Cambios

Esto es para agregar cambios al ultimo commit, sin realizar uno nuevo. 

\# sin editar el mensaje del último commit  
git commit --amend --no-edit

\# editando el mensaje del último commit  
git commit --amend -m "nuevo mensaje para el último commit"

\# eliminar el último commit  
git reset --hard HEAD~1