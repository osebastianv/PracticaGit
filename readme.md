# EJERCICIO 1

## �Qu� comando utilizaste en el paso 11? �Por qu�?

git reset --hard HEAD~1

� Con reset movemos la rama a un commit espec�fico (sin perder los cambios realizados en el working copy).

� Con --hard obligamos a que se pierdan esos cambios en el working copy.

� Con HEAD~1 retrocedemos 1 posici�n en los commits realizados (en este caso su commit padre).

El commit que hemos deshecho se queda hu�rfano.

Alternativa:
	git reset HEAD~1
	git checkout -- git-nuestro.md 

� Con reset movemos la rama a un commit espec�fico (sin perder los cambios realizados en el working copy).

� Con checkout �fichero deshacemos los cambios de ese fichero.

## �Qu� comando o comandos utilizaste en el paso 12? �Por qu�?

git reset --hard id

� Con reset movemos la rama a un commit espec�fico (sin perder los cambios realizados en el working copy).

� Con --hard obligamos a que se pierdan esos cambios en el working copy.

� Id. Para obtener el id del commit hu�rfano, utilizamos la instrucci�n git reflog:

7a02512 HEAD@{0}: reset: moving to HEAD~1

a749646 HEAD@{1}: commit: Modificacion 1 git-nuestro (punto 9)

utilizamos el id a749646 o bien HEAD@{1}.

## El merge del paso 13, �Caus� alg�n conflicto? �Por qu�?

No. La rama styled ya conten�a la rama master, por lo que no ha hecho nada a efectos pr�cticos.

## El merge del paso 19, �Caus� alg�n conflicto? �Por qu�?

Si. Porque dos ramas distintas han modificado varias l�neas del mismo fichero (en este caso todas las l�neas), por lo tanto, al haber diferencias en la misma l�nea, git no sabe distinguir cu�l es la buena. Esa tarea recae en el usuario. Una vez resuelto, git add y git commit.

## El merge del paso 21, �Caus� alg�n conflicto? �Por qu�?

No. Porque la rama styled ya conten�a la rama m�ster. Se actualiza master al contenido de styled.

## �Qu� comando o comandos utilizaste en el paso 25?

git log --graph --decorate --pretty=oneline

Se podr�a crear un alias ade este repositorio solamente:

git config alias.graph �log --graph --decorate --pretty=oneline�

o bien un alias que afecte a todos los repositorios:

git config �global alias.graph �log --graph --decorate --pretty=oneline�

## El merge del paso 26, �Podr�a ser fast forward? �Por qu�?

Si. Porque title contiene a master, por lo tanto, actualizar�a m�ster al contenido de title sin necesidad de tener un nuevo commit.
Nota: he hecho este merge dos veces: la primera vez he cometido un error ortogr�fico en el mensaje y lo he vuelto para atr�s para ponerlo bien. :-)

## �Qu� comando o comandos utilizaste en el paso 27?

git reset HEAD^1. Yo creo que tambi�n deber�a funcionar con git reset HEAD~1

## �Qu� comando o comandos utilizaste en el paso 28?

git checkout -- git-nuestro.md

## �Qu� comando o comandos utilizaste en el paso 29?

git branch -D title

no te permite �d porque la rama no est� completamente �mergeada� (integrada en otra rama).

## �Qu� comando o comandos utilizaste en el paso 30?

git reflog

f1adeaf HEAD@{5}: commit: Modificacion 3 git-nuestro: titulo (punto 23)

git reset --hard f1adeaf

Tambi�n podr�amos haber puesto git reset --hard HEAD@{5}
## �Qu� comando o comandos usaste en el paso 32?

git reflog

7a02512 HEAD@{20}: commit (initial): Crear archivo git-nuestro

git reset --hard 7a02512

Tambi�n podr�amos haber puesto git reset --hard HEAD@{20}

## �Qu� comando o comandos usaste en el punto 33?

git reflog

f1adeaf HEAD@{1}: reset: moving to f1adeaf

f1adeaf HEAD@{7}: commit: Modificacion 3 git-nuestro: titulo (punto 23)

git reset --hard f1adeaf

Tambi�n podr�amos haber puesto git reset --hard HEAD@{1} o bien HEAD@{7}

## Nota:

� El �ltimo punto (35) he dejado el HEAD en el commit al que apunta la etiqueta htmlify, no se hace referencia a que se mueva la rama master. Por lo tanto, HEAD se queda en estado �detached HEAD� (no apunta a ninguna rama).

