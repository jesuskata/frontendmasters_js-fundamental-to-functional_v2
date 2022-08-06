# Property Access - Acceso a propiedades

Data

```javascript
// Objeto literal - Objeto literal
var person = {};
```

Assignments with dots

```javascript
var person = {};
person.name = "Mrs. White";

var person = {
  "name" = "Mrs. White" // De hecho, no necesitamos las comillas en la propiedad name
};
```

En qué otros lugares has visto el uso del punto en JS?

+ Cuando accedemos a un método de un objeto
+ En las funciones
+ En las promesas (.then)
+ En métodos de arreglos
+ En métodos de prototipos
+ Métodos nativos ([].push)
+ Métodos de strings (.split)
+ Spread operator (...object)

Por lo tanto, algo importante que grabarse es que todo lo que use punto en JS es un OBJETO.

```javascript
var person = {};
person.name = "Mrs. White";

person.name; // Qué valor devolverá?: "Mrs. White"
```

De acuerdo al ejemplo de arriba, al escribir `person.name`, lo que estamos haciendo es ver qué contiene la variable en caso de existir, es por ello que devuelve el valor. Una signación, solo es considerada como tal cuando se hace explícitamente a través del signo `=`.

```javascript
var person = {};
person.name = "Mrs. White";

var who = person.name;

who; // Qué valor devolverá?: "Mrs. White"

person.name = "Mr. White";

who; // Qué valor devolverá?: "Mrs. White"
```

Los valores primitivos son todos aquellos que no son objetos, en este caso: string, number, null, undefined, boolean.

Así que, en este caso, debemos entender que un valor puede ser asignado por `valor` o por `referencia`.

Los valores primitivos siempre son pasados por `valor`, mientras que los valores no-primitivos siempre son pasados por `referencia`. Por lo tanto, el ejemplo de "Mrs. White", es un ejemplo de pasar un valor por `valor`, eso hace que en cada lugar este genere su propio espacio en memoria.

Mientras que los apuntadores en la memoria para los objetos, siempre se comparten, de tal manera que si cambias un objeto, este va a ser afectado en todos los lugares donde se haya asignado.

Aquí el por qué la sugerencia de que no se `mute` (actualizar y cambiar) un objeto (o mejor dicho una estructura de datos), sino que lo metas a una función para que dentro crees una copia, la modifiques a modo que quieras, pero al final devuelvas la copia y no la referencia del objeto original.

```javascript
var person = {};
person.name = "Mrs. White";

var who = person.name;

person.name = "Mr. White";

who.story; // Qué valor devolverá?: undefined
```
