##Respuestas Práctica GIT

**11)¿Qué comando utilizaste en el paso 11?**
   
   `git reset --hard HEAD~1`  
    
    HEAD is now at bce4477 Primer commit creamos git-nuestro  

 

**¿Por qué?**

     
 Utilizando reset `--hard` deshago los cambios que había en mi working 
 copy, es decir, deshago todos los cambios y con `HEAD~1` le indico que 
 lo haga en el último commit. De esta forma le estoy indicando que deje 
 todo como estaba antes de realizar el último commit. 
     

**12) Rehacer el último commit (el que acabamos de deshacer)**  
     **¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**  

   
1º Utilizo `git reflog` para ver todo lo que hemos hecho en el 
repositorio.  
2º Localizo el identificador de lo que hemos deshecho  
3º `git reset --hard` con el identificador del commit que quiero 
recuperar.    
Lo hago con `--hard` para que me modifique mi working copy y recuperarlo 
todo.



**13) Hacer un merge con ‘master’ (styled absorbe a master)**  
   **El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**  

    
    No ha causado ningún conflicto, porque no ha habido cambios.
    


**19) Hacer un merge de “htmlify” en “styled” (styled absorbe a 
htmlify)**
    **El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**

    
    Si, ha causado un conflicto. Ha sido porque hemos modificado el 
mismo archivo en ambas ramas y hemos hecho modificaciones
    en lineas comunes en ambos ficheros. Por ello nos indica que debemos 
ser nosotros quienes le digamos a Git con que líneas nos 
    quedamos, en caso de valernos todas, las dejaríamos, pero debemos 
ser nosotros los que en líneas comunes le indiquemos cuales 
    valen y cuales deshacemos. Una vez modificado el archivo, ya le 
podemos decir a Git que está solucionado el conflicto.  
    
    

**21) Desde “master”, hacer un merge con “styled”**  
   **El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**

    
    No, no causo ningún conflicto, porque el contenido de ambos ficheros 
era el mismo.
    fast-fordward al ser un listado.


**25) Dibujar el diagrama**
    **¿Qué comando o comandos utilizaste en el paso 25?**

   `git log --graph --decorate --pretty=oneline`    
     
     
   Con estos comandos muestro el gráfico con los punteros y cada commit 
resumido en una línea.
   


**26) Hacer un merge “no fast-forward” de “title” en “master” (master 
absorbe a title)**
    **El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**

    
    Si, podría ser fast-forward porque tenemos acceso a toda la lista de 
commit de la rama en la que estamos.
    


**27)Deshacer el merge (sin perder los cambios del working copy)**
   **¿Qué comando o comandos utilizaste en el paso 27?**

    
   ` git reset HEAD~1`
    

**28) Descartar los cambios**
   ** ¿Qué comando o comandos utilizaste en el paso 28?**
  
   
   Para descartar los cambios se puede utilizar:
 
   `git checkout -- git-nuestro.md` 

   


**29) Eliminar la rama “title”**  
    **¿Qué comando o comandos utilizaste en el paso 29?**

    
   He utilizado `git branch -D title` para borrar completamente la rama 
title.
    


**30) Rehacer el merge que hemos deshecho**  
   **¿Qué comando o comandos utilizaste en el paso 30?**

    
   Lo he hecho utilizando este orden de comandos

   `git reflog`   para ver la posición del commit a la que quiero mover 
el puntero  
   `git reset --hard d0b4146`  que es la posición donde hicimos el merge 
y quiero volver.
    

**32) Volver al commit inicial cuando se creó el poema**  
   **¿Qué comando o comandos usaste en el paso 32?**

   
   Podemos hacerlo de varias formas, utilizando `git log` para ver el 
histórico de commit que tenemos y así poder coger la referencia del 
mismo o con `git reflog` como he hecho varias veces durante la práctica, 
cogeremos el identificador de la posición en la que se encuentra el 
commit inicial.  
   Posteriormente para volver a esa posición como estaba podemos 
utilizar `git reset --hard` y seguido de la referencia, en mi caso, `git 
reset --hard bce4477` al identificador del commit o como he hecho yo en 
este caso `git checkout bce4477` que nos lleva a la posición que le 
indicamos, situando el HEAD en el primer Commit.
 
   `git reflog`  para ver la posición inicial.  
   `git checkout bce4477` 
   

**33) Volver al estado final, cuando pusimos título al poema**  
  **¿Qué comando o comandos usaste en el punto 33?**

  

  `git reset --git reflog --> 34b5362 HEAD@{5}: commit: Añadimos Titulo 
git-nuestro rama title`  para ver la posición del estado final  
  `git checkout 34b5362`  nos posicionamos y dejamos como estaba.

  
  
> También podíamos utilizar el comando  
>   $ git reset --hard 34b5362  
>   HEAD is now at 34b5362 Añadimos Titulo git-nuestro rama title
> 
> 
 

> No estoy seguro si debemos poner todos los pasos dados en la práctica
  por si fuese así los pongo a continuación.




##Pasos dados en cada punto de la práctica

**1) Crear un repositorio**

  
    cd desktop
    git clone https://github.com/DanielRA76/PracticasGIT.git
    cd PracticasGIT
    git init  
  

**2) Crear un archivo git-nuestro.md con el contenido**

  
  `nano git-nuestro.md`
  
  Como es la primera práctica no estoy seguro si el documento readme lo 
puedo poner al final de la práctica o debe ser ahora.  
  Lo voy a crear también ahora junto con git-nuestro.md

  
  `nano readme.md`

  
**3) Añadir git-nuestro.md al staging area**

  
    git add git-nuestro.md
    git add readme.md
    


**4) Mover lo que hay en el staging area al repositorio**

 
   `git commit -m "Primer commit creamos git-nuestro"`
  

**5) Crear una rama llamada “styled”**

  
  `git branch styled`
  


**6) Listar las ramas que hay en el repositorio**

  
  `git branch`
  
> MINGW64 ~/desktop/PracticaGIT (master)  
> $ git branch  
> * master  
>   styled


**7) Moverse a la rama “styled”**

  
  `git checkout styled`
  
  

**8) Comprobar que se está en la rama correcta**

  
  `git branch`
  

> MINGW64 ~/desktop/PracticaGIT (master)  
> master  
> * styled  


**9) Modificar en el archivo git-nuestro.md:**

  
  `nano git-nuestro.md`
  

**10) Añadir los cambios al staging área y luego pasarlos al 
repositorio**

  
    git add git-nuestro.md
    git commit -m "2º commit modificamos git-nuestro rama styled"
  
**
11) Deshacer el último commit (perdiendo los cambios realizados en el 
working copy)**

  
  `git reset --hard HEAD~1`
  

**12) Rehacer el último commit (el que acabamos de deshacer)**

  
    git reflog
    git reset --hard 5f50bf0
  
  
> git reflog  
> bce4477 (HEAD -styled, master) HEAD@{0}: reset: moving to HEAD~1  
> 5f50bf0 HEAD@{1}: commit: 2º commit modificamos git-nuestro rama 
styled  
> bce4477 (HEAD -styled, master) HEAD@{2}: checkout: moving from master 
to styled  
> bce4477 (HEAD -styled, master) HEAD@{3}: commit (initial): Primer 
commit creamos git-nuestro  



**13) Hacer un merge con ‘master’ (styled absorbe a master)**

  
  `git merge master`  
  
   *Already up to date.*



**14) Volver a la rama master**

  
  `git checkout master`
  


**15) Crear una nueva rama llamada “htmlify”**

  
  `git branch htmlify`
  


**16) Cambiar a la rama htmlify**

  
  `git checkout htmlify`
  


**17) Modificar en el archivo git-nuestro.md:**

  
  `nano git-nuestro.md`
  

**18) Hacer un commit**
  
  
    git add git-nuestro.md
    git commit -m "modificamos git-nuestro rama htmlify"
  

**19) Hacer un merge de “htmlify” en “styled” (styled absorbe a 
htmlify)**

  
    git checkout styled
    git merge htmlify
  

> 	git merge htmlify
> 	Auto-merging git-nuestro.md
> 	CONFLICT (content): Merge conflict in git-nuestro.md
> 	Automatic merge failed; fix conflicts and then commit the 
result.

  


**20) Si hay conflictos, deberemos resolverlos quedándonos con el 
contenido de la rama “styled”.**

  
    nano git-nuestro.md
    git add git-nuestro.md
    git commit -m "Merge conflictos quedamos rama styled"
  

  [styled 049073c] Merge conflictos quedamos rama styled

  
 
***modificamos fichero quedándonos solo con contenido de rama styled*** 

  > $ cat git-nuestro.md  
> 
>   \*Git* nuestro que estas en los repos
> 
>   Comprimidos sean tus \*commits*
> 
>   Venga a nosotros tu \*log*
> 
>   En el local como en el \*remote*
> 
>   Danos hoy nuestro \*pull* de cada día
> 
>   Perdona nuestros \*conflictos*
> 
>   No nos dejes caer en \*detached HEAD*
> 
>   y líbranos de \*SVN*  
>
>  `git commit --amend`


**21) Desde “master”, hacer un merge con “styled”**

  
    git checkout master
    git merge styled
  

 Updating bce4477..049073c  
 Fast-forward



**22) Crear una rama “title” y cambiarse a esa rama**

  
  `git checkout -b title`
  


**23) Añadir un título (a tu gusto) al archivo git-nuestro.md y hacer un 
commit.**

    
    nano git-nuestro.md
    git add git-nuestro.md
    git commit -m "Añadimos Titulo git-nuestro rama title"
  

**24) Volver a la rama master**

  
  `git checkout master`
  


**25) Dibujar el diagrama**

  
  `git log --graph --decorate --pretty=oneline`
  

> git log --graph --decorate --pretty=oneline  
> *   049073c780ceb5dd7a7e9a13996f2b00764a1fa8 (HEAD -master, styled) 
Merge conflictos quedamos rama styled  
> |\  
> | * 340f46b7082476104fd5ecd06790e3c1778fe86b (htmlify) modificamos 
git-nuestro rama htmlify  
> * | 5f50bf020009f690259399ab1f2c8e186c6724c9 2º commit modificamos 
git-nuestro rama styled  
> |/  
> * bce44774ef8d74f23bd7b17e62994d8673709eed Primer commit creamos 
git-nuestro  



**26) Hacer un merge “no fast-forward” de “title” en “master” (master 
absorbe a title)**

  
   `git merge --no-f title`
  

**27) Deshacer el merge (sin perder los cambios del working copy)**

  
  `git reset HEAD~1`
  

**28) Descartar los cambios**

  
  `git checkout -- git-nuestro.md`
  

**29) Eliminar la rama “title”**

  
  `git branch -D title`
  


**30) Rehacer el merge que hemos deshecho**

  
    git reflog
    git reset --hard d0b4146
  

> git reflog  
> 049073c (HEAD -master, styled) HEAD@{0}: reset: moving to \HEAD~1  
> d0b4146 HEAD@{1}: merge title: Merge made by the 'recursive' strategy.  
> 049073c (HEAD -master, styled) HEAD@{2}: checkout: moving from title 
to master  
> 34b5362 HEAD@{3}: commit: Añadimos Titulo git-nuestro rama title  
> 049073c (HEAD -master, styled) HEAD@{4}: checkout: moving from master 
to title  
> 049073c (HEAD -master, styled) HEAD@{5}: merge styled: Fast-forward  
> bce4477 HEAD@{6}: checkout: moving from styled to master  
> 049073c (HEAD -master, styled) HEAD@{7}: commit (merge): Merge 
conflictos quedamos rama styled  
> 5f50bf0 HEAD@{8}: checkout: moving from htmlify to styled  
> 340f46b (htmlify) HEAD@{9}: commit: modificamos git-nuestro rama 
htmlify    
> bce4477 HEAD@{10}: checkout: moving from master to htmlify  
> bce4477 HEAD@{11}: checkout: moving from styled to master  
> 5f50bf0 HEAD@{12}: reset: moving to 5f50bf0  
> bce4477 HEAD@{13}: reset: moving to \HEAD~1  
> 5f50bf0 HEAD@{14}: commit: 2º commit modificamos git-nuestro rama 
styled  
> bce4477 HEAD@{15}: checkout: moving from master to styled  
> bce4477 HEAD@{16}: commit (initial): Primer commit creamos git-nuestro  



**31) Volver a master y eliminar el resto de ramas**

  
    git branch
    git branch -D htmlify
    git branch -D styled
  

**32) Volver al commit inicial cuando se creó el poema**

  
    git reflog  -->  bce4477 HEAD@{17}: commit (initial): Primer commit 
creamos git-nuestro  
    git checkout bce4477 
  

**33) Volver al estado final, cuando pusimos título al poema**

  
    git reflog --> 34b5362 HEAD@{5}: commit: Añadimos Titulo git-nuestro 
rama title  
    git checkout 34b5362

> Previous HEAD position was bce4477 Primer commit creamos git-nuestro  
> HEAD is now at 34b5362 Añadimos Titulo git-nuestro rama title

  

**34) Crear los siguientes tags:**

  -inicial: en el primer commit  
  -styled: modificación del paso 10  
  -htmlify: modificación del paso 17-18  
  -title: modificación del paso 30  

   
    git tag inicial bce4477
    git tag styled 5f50bf0
    git tag htmlify 340f46b
    git tag title d0b4146
  

**35) Ir al tag htmlify**

  
  `git checkout htmlify`
  

