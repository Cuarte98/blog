---
title: "Renovando git: bye bye, checkout"
date: "2021-04-25"
---

Hay una serie de comandos de git que nos sabemos de memoria, pero existe uno en particular que tiene múltiples usos: `git checkout`.

Ah pero que tenga múltiples uso significa que es más practico. Si, y más probable que cometas errores

`git checkout` es un comando que podemos usar para crear y borrar branches, navegar entre ellas y eliminar cambios que no están en estado de stage.

Ahora, la gente de git se despabiló y se dio cuenta de que sería mejor tener comandos más verbosos para las distintas acciones que hacemos con nuestro controlador de versiones.

Cada uno de los siguientes comandos que te voy a mostrar realizan la misma acción que hacíamos antes con `git checkout` pero escrito de una forma más amigable

### Creando ramas: git branch

Cuando queremos crear una rama, es normal que nos encontremos usando el comando `git checkout mi-rama`. Para hacerlo más entendible, lo vamos a cambiar por `git branch mi-rama`

### Navegando entre ramas: git switch

Es normal cambiar a una rama de un colega para revisar sus cambios o querer volver a `develop` para tener los últimos cambios. Yo siempre usé para esto `git checkout rama-de-mi-colega`. hasta que descubrí que existe un comando que es mucho más claro: `git switch rama-de-mi-colega`

### Borrando cambios: git restore

Cuando ya separé cuales son los cambios que van en el commit, lo demás se descarta, y para descartar recurrimos al `git checkout -- .`. Hoy en día git te recomienda utilizar `git restore .`

## Conclusión

Utilizar el mismo comando para todo puede ser super practico, pero si recién estas empezando, puede que te provoque un par de USB (USB? ABC? ACV!). Nuestros comandos y nuestros procesos deben dejar claras nuestras intenciones, de esta manera podemos compartir un paso a paso y ser lo más claros posibles en nuestra comunicación técnica.

Fuentes:

[git branch](https://git-scm.com/docs/git-branch)
[git switch](https://git-scm.com/docs/git-switch)
[git restore](https://git-scm.com/docs/git-restore)
