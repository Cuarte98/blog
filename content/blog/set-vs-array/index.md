---
title: El primo del Array ¿Qué es un set?
date: "2021-07-25"
---

Un set es un tipo de objeto incluido en ES2015 que tiene semejanzas con un array:

- Contiene una lista de datos de cualquier tipo
- Es iterable
- Permite el uso del operador spread

Pero también diferencias:

- Sus datos no se repiten
- No cuenta con los métodos de Array (map, some, filter)
- Es un poco más performante

## ¿Cómo crear un Set?

Un Set es un tipo de objeto, por lo que su sintaxis es la misma que la de un constructor:

```javascript
const unSetVacío = new Set()
```

Si queremos inicializar nuestro Set con valores, deberemos pasar como argumento un array

```javascript
const redesSociales = new Set(["Facebook", "Twitter", "Fotolog"])
```

## Qué métodos tiene un Set?

El objeto Set tiene metodos propios para agregar, borrar y comprobar datos

### Agregar datos a un Set

Para agregar datos a un Set, contamos con el método `.add()`

```javascript
redesSociales.add("Instagram")
redesSociales.add("MySpace")
console.log(redesSociales) // Set ['Facebook', 'Twitter', 'Fotolog', 'Instagram', 'MySpace']
```

¿Qué pasa si por error duplicamos un dato? ¡Absolutamente nada! Los Set solo permiten valores únicos

```javascript
redesSociales.add("Facebook")
console.log(redesSociales) // Set ['Facebook', 'Twitter', 'Fotolog', 'Instagram', 'MySpace']
```

### Eliminar datos de un Set

Para eliminar datos de un Set, contamos con el método `.delete()`. Si retornamos o hacemos `console.log` al usar este metodo, nos retornará un valor booleano para avisarnos de que pudo borrar el dato que le dijimos

```javascript
// RIP Fotolog y MySpace
redesSociales.delete("Fotolog") // true
redesSociales.delete("MySpace") // true
console.log(redesSociales) // Set ['Facebook', 'Twitter', 'Instagram']

//Intentemos borrarlos otra vez, nos retornará false ya que no existen más
redesSociales.delete("Fotolog") // false
redesSociales.delete("MySpace") // false
```

### Comprobar si un Set contiene un dato

Para comprobar si existe un dato dentro de un Set, usaremos el método `.has()` que nos retornará un valor booleano

```javascript
redesSociales.has("Instagram") // true
redesSociales.has("Fotolog") // false
redesSociales.has("LinkedIn") // false
```

### Comprobar el tamaño de un Set

Para saber qué tamaño tiene un Set, contamos con la propiedad `.size` (¡¿Por qué no le pusieron `.length` como a los Arrays?!)

```javascript
redesSociales.size // 3
```

## Cómo iterar un Set?

Un Set puede ser iterable casi como cualquier objeto, por ejemplo, con un `for..of`

```javascript
for (let redSocial of redesSociales) {
  console.log(redSocial)
}
```

También podemos hacer uso de los métodos `.values()` o `.keys()` que retornan un nuevo objeto iterable con los datos del Set (Sí, ambos métodos hacen lo mismo).

## Cómo vuelvo al modo Array?!

Si tenes necesidad de transformar tu Set en un Array, podemos usar dos métodos:

- Usar el metodo `.from()` del objeto `Array`

```javascript
const redesSocialesArray = Array.from(redesSociales)
```

- La vieja confiable: el spread operator

```javascript
const redesSocialesSpread = [...redesSociales]
```

## Conclusión

Hoy aprendimos qué es un Set, cómo modificarlo y cómo convertirlo en Array. Hay más métodos que no te conté para no hacerla muy larga. Al final te voy a dejar la documentación que utilicé para poder escribir esto. Te invito a que la leas, investigues, juegues y practiques.

## ¡Gracias por llegar hasta acá!

Fuentes:

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set

https://javascript.info/map-set
