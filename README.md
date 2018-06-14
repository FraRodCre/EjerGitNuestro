# Ejercicio 1

**1. ¿Qué comando utilizaste en el paso 11? ¿Por qué?**

El comando utlizado en el paso 11, *Deshacer el último commit (perdiendo los cambios realizados en el working copy)*, ha sido:

```git
$ git reset --hard HEAD~1
```

El motivo de utilizar *git reset --hard HEAD~1*, es eliminar el contenido del **working copy**, ya que, si en lugar de utilizar el comando indicado, se hubiera utilizado únicamente:

```git
$ git reset HEAD~1**
```
Se habría mantenido el contenido del working copy.

Los comandos utilizados indican lo siguiente:

> - <u>**reset:**</u> Indica que se va a deshacer un commit.
> - <u>**- -hard:**</u> Indica que a "restaurar" lo que había en el working directory para dejarlo como estaba antes de las modificaciones.
> - <u>**HEAD~N:**</u> Indica que va deshacer *N* commits hacia atrás, en este caso **sólo 1, el último**.

---

**2. ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**

Los comando utlizados en el paso 12, *Rehacer el último commit (el que acabamos de deshacer)*, han sido:

```git
$ git log
$ git reflog
$ git reset --hard a689be8
```

El motivo de utilizar *git reset --hard sdfdsf*, es restaurar al estado original el contenido del **working copy (en nuestro caso el archivo git-nuestro.md)**, ya que, si en lugar de utilizar el comando indicado, se hubiera utilizado únicamente:

```git
$ git reset a689be8
```
Se habría mantenido los últimos cambios realizados y no volveríamos al estado original.

Los comandos utilizados indican lo siguiente:

> - <u>**reset, - -hard:**</u> Se explicó su uso en el apartado 1 del ejercicio.
> - <u>**log:**</u> Muestra los commits realizados.
> - <u>**Identificador del commit a restaurar:**</u> Es el hash que identifica el commit que vamos a restuarar, en este caso, .

---

**3. El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**

El comando utlizado en el paso 13, *Hacer un merge con ‘master’ (styled absorbe a master)*, ha sido:

```git
$ git merge master
```
 
 Con ello, conseguimos absober el contenido de *master* en *styled*. Al ser hija la rama *styled* de la rama *master* esta absorbe el contenido de su padre sin generar conflicto 

**4. El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**

Al realizar el paso 19, *Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)*, primero hemos tenido que ir a la rama *styled* mediante:

```git
$ git checkout styled
```
Y luego, hacer el merge a la rama *htmlify* con el siguiente comando:

```git
$ git merge htmly
```

Una vez completado el paso 19, se ha generado un conflicto debido a que ambas ramas a pesar de tener el mismo padre, *master*, son dos ramas diferentes de este, "sin visibilidad" entre ellas y se ha modificado el mismo archivo en las mismas líneas.

---

**5. El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**

Al realizar el paso 21, *Desde “master”, hacer un merge con “styled”*, primero hemos tenido que ir a la rama *master* mediante:

```git
$ git checkout master
```
Y luego, hacer el merge a la rama *styled* con el siguiente comando:

```git
$ git merge styled
```

Una vez completado el paso 21, no se han generado conflictos, ya que el padre(master) ha absorbido al hijo (styled) mediante fast-forward moviéndose junto con el puntero *HEAD* a la misma rama y commit del hijo.

---

**6. ¿Qué comando o comandos utilizaste en el paso 25?**

Para relizar el paso 25, *Dibujar el diagrama*, se ha utilizado en el mismo orden, los comandos indicados a continuación:

```git
$ git checkout master
$ git log --graph --decorate --pretty=oneline
```

---

**7. El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**

El merge del paso 26, *Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)*, ha sido realizdo con:

```git
$ git merge --no-ff title
```

Aunque tambíen se podría haber realizado con:

```git
$ git merge title
```
Y se hubiera creado mediante fast-forward, pues al ser la rama *title* un ancestro de la rama *master*, es posible realizar el merge mediante fast-forward.

---

**8. ¿Qué comando o comandos utilizaste en el paso 27?**

Los comandos utlizados en el paso 27, *Deshacer el merge (sin perder los cambios del working copy)*, han sido:

```git
$ git log
$ git reset c60cdc1a86f4a6e84b1086f2c4d5a14711862ada
```
Donde, *c60cdc1a86f4a6e84b1086f2c4d5a14711862ada*, es el commit anterior al merge (cuando se crea el titulo en la rama title).

----

**9. ¿Qué comando o comandos utilizaste en el paso 28?**

Los comandos utlizados en el paso 28, *Descartar los cambios*, han sido:

```git
$ git reflog
$ git reset --hard d3235f1
```
Donde, *d3235f1*, es el hash correspondiente al checkout(desplazamiento) de master a title.

---

**10. ¿Qué comando o comandos utilizaste en el paso 29?**

El comando utlizado en el paso 29, *Eliminar la rama “title”*, ha sido:

```git
$ git branch -D title
```
Ya que, con el comando:

```git
$ git branch -d title
```
No es posible debido a que no se ha realizado aún el merge(lo deshicimos pasos anteriores).

---

**11. ¿Qué comando o comandos utilizaste en el paso 30?**

Los comandos utlizados en el paso 30, *Rehacer el merge que hemos deshecho*, han sido:

```git
$ git reflog
$ git reset --hard dabadb4
```

Dónde, *dabadb4*, es el hash del commit correspondiente al merge en el que se realizó el merge de title en master. 

---

**12. ¿Qué comando o comandos usaste en el paso 32?**

Los comandos utlizados en el paso 32, *Volver al commit inicial cuando se creó el poema*, han sido:

```git
$ git reflog
$ git reset --hard 601c336
```

Dónde, *601c336*, es el hash del commit correspondiente a la creación del fichero *GitNuestro.md*. 

---

**13. ¿Qué comando o comandos usaste en el paso 33?**

Los comandos utlizados en el paso 33, *Volver al estado final, cuando pusimos título al poema*, han sido:

```git
$ git reflog
$ git c60cdc1
```

Dónde, *c60cdc1*, es el hash del commit correspondiente al commit en el que se añadió por primera vez el título al fichero *GitNuestro.md*. 