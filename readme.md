# EJERCICIO 1

## ¿Qué comando utilizaste en el paso 11? ¿Por qué?

git reset --hard HEAD~1

• Con reset movemos la rama a un commit específico (sin perder los cambios realizados en el working copy).

• Con --hard obligamos a que se pierdan esos cambios en el working copy.

• Con HEAD~1 retrocedemos 1 posición en los commits realizados (en este caso su commit padre).

El commit que hemos deshecho se queda huérfano.

Alternativa:
	git reset HEAD~1
	git checkout -- git-nuestro.md 

• Con reset movemos la rama a un commit específico (sin perder los cambios realizados en el working copy).

• Con checkout –fichero deshacemos los cambios de ese fichero.

## ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

git reset --hard id

• Con reset movemos la rama a un commit específico (sin perder los cambios realizados en el working copy).

• Con --hard obligamos a que se pierdan esos cambios en el working copy.

• Id. Para obtener el id del commit huérfano, utilizamos la instrucción git reflog:

7a02512 HEAD@{0}: reset: moving to HEAD~1

a749646 HEAD@{1}: commit: Modificacion 1 git-nuestro (punto 9)

utilizamos el id a749646 o bien HEAD@{1}.

## El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

No. La rama styled ya contenía la rama master, por lo que no ha hecho nada a efectos prácticos.

## El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

Si. Porque dos ramas distintas han modificado varias líneas del mismo fichero (en este caso todas las líneas), por lo tanto, al haber diferencias en la misma línea, git no sabe distinguir cuál es la buena. Esa tarea recae en el usuario. Una vez resuelto, git add y git commit.

## El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

No. Porque la rama styled ya contenía la rama máster. Se actualiza master al contenido de styled.

## ¿Qué comando o comandos utilizaste en el paso 25?

git log --graph --decorate --pretty=oneline

Se podría crear un alias ade este repositorio solamente:

git config alias.graph “log --graph --decorate --pretty=oneline”

o bien un alias que afecte a todos los repositorios:

git config –global alias.graph “log --graph --decorate --pretty=oneline”

## El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Si. Porque title contiene a master, por lo tanto, actualizaría máster al contenido de title sin necesidad de tener un nuevo commit.
Nota: he hecho este merge dos veces: la primera vez he cometido un error ortográfico en el mensaje y lo he vuelto para atrás para ponerlo bien. :-)

## ¿Qué comando o comandos utilizaste en el paso 27?

git reset HEAD^1. Yo creo que también debería funcionar con git reset HEAD~1

## ¿Qué comando o comandos utilizaste en el paso 28?

git checkout -- git-nuestro.md

## ¿Qué comando o comandos utilizaste en el paso 29?

git branch -D title

no te permite –d porque la rama no está completamente “mergeada” (integrada en otra rama).

## ¿Qué comando o comandos utilizaste en el paso 30?

git reflog

f1adeaf HEAD@{5}: commit: Modificacion 3 git-nuestro: titulo (punto 23)

git reset --hard f1adeaf

También podríamos haber puesto git reset --hard HEAD@{5}
## ¿Qué comando o comandos usaste en el paso 32?

git reflog

7a02512 HEAD@{20}: commit (initial): Crear archivo git-nuestro

git reset --hard 7a02512

También podríamos haber puesto git reset --hard HEAD@{20}

## ¿Qué comando o comandos usaste en el punto 33?

git reflog

f1adeaf HEAD@{1}: reset: moving to f1adeaf

f1adeaf HEAD@{7}: commit: Modificacion 3 git-nuestro: titulo (punto 23)

git reset --hard f1adeaf

También podríamos haber puesto git reset --hard HEAD@{1} o bien HEAD@{7}

## Nota:

• El último punto (35) he dejado el HEAD en el commit al que apunta la etiqueta htmlify, no se hace referencia a que se mueva la rama master. Por lo tanto, HEAD se queda en estado “detached HEAD” (no apunta a ninguna rama).

