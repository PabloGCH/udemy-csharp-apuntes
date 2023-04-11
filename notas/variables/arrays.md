Arrays
=================

Los arrays se declaran de la siguientes forma:

```csharp
int[] a = new int[10];
int[] b = new int[5] { 1, 2, 3, 4, 5 };
int[] c = { 1, 2, 3, 4, 5 };
```

Para declarar un array de dos dimensiones, se utiliza la siguiente sintaxis:

```csharp
int[][] f = new int[2][];
```

o

```csharp
int[,] d = new int[2, 3];
int[,] e = new int[2, 3] { { 1, 2, 3 }, { 4, 5, 6 } };
`````

Para conseguir el número de elementos de un array, se utiliza la propiedad Length:

```csharp
int[] a = new int[10];
Console.WriteLine(a.Length); // 10
```

Y para acceder a las dimensiones de un array de dos dimensiones, se utiliza GetLongLength()

```csharp
int[,] a = new int[2, 3];
Console.WriteLine(a.GetLongLength(0)); // 2
```
