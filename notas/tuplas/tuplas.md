Tuplas
================

En csharp las tuplas son un tipo de dato que permite almacenar varios valores de diferentes tipos en una sola variable. Las tuplas son inmutables, es decir, una vez creadas no se pueden modificar.

Las tuplas se pueden crear de dos formas:

1.  Utilizando la palabra clave `Tuple` y especificando el tipo de dato de cada elemento de la tupla.

```csharp
var tupla = new Tuple<int, string, bool>(1, "Hola", true);
```

2.  Utilizando la palabra clave `Tuple` y sin especificar el tipo de dato de cada elemento de la tupla.

```csharp
var tupla = Tuple.Create(1, "Hola", true);
```


Para acceder a los elementos de una tupla.

1.  Utilizando la propiedad `ItemX` donde X es el número del elemento al que se quiere acceder.

```csharp
var tupla = Tuple.Create(1, "Hola", true);
Console.WriteLine(tupla.Item1);
Console.WriteLine(tupla.Item2);
Console.WriteLine(tupla.Item3);
```


