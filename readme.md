#Solución a la práctica

##¿Qué comando utilizaste en el paso 11? ¿Por qué?
Comando: 

**git reset --hard HEAD~1**

Con el comando *reset* podemos desplazarnos por la lista de commits. En esta ocasión el modificador *'HEAD~1' hace referencia al commit anterior y  *'--hard'* hace perder los datos del working copy.

##¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
Comandos:

**git reflog**

**git reset --hard 1b29ab6**

En este caso recurro a *'git reflog'* para encontrar el hash del último commit pues éste no aparece en el log. En la lista que me ofrece reflog busco empezando por el último commit *HEAD@{0}* y siguiendo hacia atrás el histórico. El commit que me interesa es el siguiente al que tiene como texto *'moving to HEAD~1'* que representa al comando 11. Tomo el hash corto y se lo paso al *'git reset --hard' para deshacer el commit.

NOTA: En vez de el hash corto también podría haber utilizado la referencia relativa que muestra *reflog* en cada commit. En concreto la referencia *HEAD@{1} que se refiere al commit anterior a el que nos encontramos:
Comando:

**git reset --hard HEAD@{1}

##El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

Este merge no causó ningún conflicto porque la rama *styled* contiene todos los cambios (*commits*) incluidos en la rama *master*. De hecho cuando lanzo el comando *merge* de ambas ramas, git me contesta que todo está al día (*'Already up-to-date'*). El puntero *HEAD* se mantiene en *styled*.

##El merge del paso 19, ¿Cuasó algún conflicto? ¿Por qué?

Este merge sí crea un conflicto porque une dos ramas en las que se modifica las mismas líneas (en una rama hay notación markdown y en otra etiquetas HTML) de un mismo archivo (*git-nuestro.md). Para completar el merge habrá que resolver los conflictos, y añadir esta versión del archivo con los conflictos resueltos al repositorio.

##El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

No hay ningún conflicto porque el puntero de la rama que absorbe (*master*) se quiere 'mergear' con otro situado por encima en una lista. Git resuelve esta situación realizando un *fast-forward* en el que avanza el puntero *master* al mismo sitio donde está el puntero de la rama con la que se hace el merge (*styled*). Como el archivo *git-nuestro.md* contiene todas las modificaciones en ambas ramas no existe conflicto.

##¿Qué comando o comandos utilizaste en el paso 25?
Comando:

**git log --graph --decorate --pretty=oneline**

Escribir un comando tan largo como este puede resultar tedioso durante el trabajo diario. Por ello, es muy práctico crearse un alias de git que nos permita lanzarlo con unos pocos caracteres.

##El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Podría ser fast forward perfectamente porque la rama *TITLE* ya contiene todas las modificaciones de *MASTER*. Así, como la rama *TITLE* está por delante de *MASTER*, Git avanza el puntero de *MASTER* al commit donde está *TITLE* haciendo un merge fast forward.

##¿Qué comando o comandos utilizaste en el paso 27?
Comando:

**git reset HEAD~1**

Muevo el puntero al anterior commit. Como no he usado el modificador *--no-ff* se mantienen los cambios en el working copy).

##¿Qué comando o comandos utilizaste en paso 28?
Comando:

**git checkout -- git-nuestro.md**

Como comenté en una pregunta anterior, también se podría haber utilizado la referencia relativa HEAD@{n} (donde n es un entero cero o positivo) que obtenemos al usar el comando *'git reflog'.

##¿Qué comando o comandos utilizaste en el paso 29?
Comando:

**git branch -D title**

##¿Qué comando o comandos utilizaste en el paso 30?
Comandos:

**git reflog**

**git reset --hard dffb31f**

De nuevo también podríamos haber usado la referencia relativa *HEAD@{n}* que ofrece el comando *reflog*.

##¿Qué comando o comandos utilizaste en el paso 32**
Comandos:

**git reflog**

**git reset --hard 7cd30a9**

Los comandos anteriores mueven también el puntero de la rama actual (*master*) al commit en cuestión. No me queda claro si esto se pide en el ejercicio por lo que en caso de no ser necesario podríamos haber hecho también un chekcout al commit en cuestión:

**git checkout 7cd30a9**

##¿Qué comando o comandos utilizaste en el paso 33?
Comandos:

**git reflog**

**git reset --hard 0d2340e**

Al igual que en la pregunta anterior, en caso de no ser necesario mover el puntero de la rama master (no me queda claro) podríamos haber usado un *checkout*:

**git checkout 0d2340e**

