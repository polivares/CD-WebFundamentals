# Comandos Git

## 1. git clone

- Comando para descargar el código fuente existente desde un repositorio remoto (como Github u otros). 
- Git clone hace una copia idéntica de la última versión de un proyecto existente en un repositorio y la guarda en el computador.

```console
    git clone <https://link-con-nombre-del-repositorio>
    git clone nombredeusuario@host:/path/to/repository
```

## 2. git branch

- Creación de una rama.

```console
    git branch <nombre-de-la-rama>
```

## 3. git checkout

- Se usa este comando para cambiar de rama

```console
git checkout <nombre-de-la-rama>
```

## 4. git push 

- Este comando creará una rama en local. 
- Para enviar (push) la nueva rama al repositorio remoto, necesitarás usar el siguiente comando:

```console
git push <nombre-remoto> <nombre-rama>
git push  origin <master>
```

## 5. git branch

- Se usa este comando para ver una rama.


## 6. git branch -d

- Se usa para borrar una rama

```console
git branch -d <nombre-de-la-rama>
```

Ojo, antes de cambiar de rama, se deben guardar los cambios de la rama actual. La rama a la que uno se quiere cambiar debe existir localmente.


## 7. git status

- Este comando entrega mucha información sobre la rama en la que nos encontramos. Nos indica:

    * Si la rama actual está actualizada
    * Si hay algo para confirmar, enviar o recibir (pull).
    * Si hay archivos en preparación (staged), sin preparación(unstaged) o que no están recibiendo seguimiento (untracked)
    * Si hay archivos creados, modificados o eliminados

## 8. git add

- Al crear, modificar o eliminar un archivo de una rama se hace primero de forma local. Para que estos cambios se reflejen en la rama online se debe ejecutar el comando git add

```console
git add –all
git add -A
```

## 9. git commit

- Este comando permite guardar los cambios en la rama local. Se debe agregar un mensaje al momento de guardar los cambios.

```console
git commit -m "mensaje de confirmación" 
```

## 10. git push

- Permite subir los cambios locales a la rama online.

```console
git push <nombre-remoto> <nombre-de-tu-rama>
```

## 11. git merge

- Permite integrar los cambios hechos de forma local a una misma rama que ha sido utilizada por varios usuarios a la vez.

```console
git merge <nombre-de-la-rama>
```

## 12. git init

- Crear un nuevo repositorio local de GIT

```console
git init
git init [nombre del proyecto]
```