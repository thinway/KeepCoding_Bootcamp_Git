#Solución a la práctica

##¿Qué comando utilizaste en el paso 11? ¿Por qué?
Comando: 
**git reset --hard HEAD~1**

Con los modificadores *'--hard HEAD~1'* se deshacen los cambios introducidos en el último commit dejando el working copy limpio.

##¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
Comandos:
**git reflog**
**git reset --hard 1b29ab6**

En este caso recurro a *'git reflog'* para encontrar el hash del último commit pues éste no aparece en el log. En la lista que me ofrece reflog busco empezando por el último commit *HEAD@{0}* y siguiendo hacia atrás el histórico. El commit que me interesa es el siguiente al que tiene como texto *'moving to HEAD~1'* que representa al comando 11. Tomo el hash corto y se lo paso al *'git reset --hard' para deshacer el commit.

##El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

Este merge no causó ningún conflicto porque la rama contiene todos los cambios. De hecho cuando lanzo el comando git me contesta *'Already up-to-date'*. El puntero *HEAD* se mantiene en *styled*.

##El merge del paso 19, ¿Cuasó algún conflicto? ¿Por qué?

Este merge sí crea un conflicto porque se une dos ramas en las que se modifica las mismas líneas (en una rama hay notación markdown y en otra etiquetas HTML) de un mismo archivo (*git-nuestro.md).

##El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

No hay ningún conflicto porque el puntero de la rama que absorbe (*master*) avanza al mismo sitio donde está la rama con la que se hace el merge (*styled*), ya que el archivo *git-nuestro.md* contiene todas las modificaciones.

##¿Qué comando o comandos utilizaste en el paso 25?
Comando:
**git log --graph --decorate --pretty=oneline**

##El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Podría ser fast forward perfectamente porque la rama *TITLE* ya contiene todas las modificaciones de *MASTER* por lo cual como la rama *TITLE* por delante de *MASTER*, Git avanza el puntero de *MASTER* al commit donde está *TITLE*.

##¿Qué comando o comandos utilizaste en el paso 27?
Comando:
**git reset HEAD~1**

##¿Qué comando o comandos utilizaste en paso 28?
Comando:
**git checkout -- git-nuestro.md**

##¿Qué comando o comandos utilizaste en el paso 29?
Comando:
**git branch -D title**

##¿Qué comando o comandos utilizaste en el paso 30?
Comandos:
**git reflog**
**git reset --hard dffb31f**

##¿Qué comando o comandos utilizaste en el paso 32**
Comandos:
**git reflog**
**git reset --hard 7cd30a9**

##¿Qué comando o comandos utilizaste en el paso 33?
Comandos:
**git reflog**
**git reset --hard 0d2340e**
