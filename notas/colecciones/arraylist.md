Array List
======================

Un array list es una lista de elementos que se almacenan en un array. La lista
tiene un tamaño que aumenta automáticamente cuando se añaden elementos a lista.

Ejemplo:

```csharp
ArrayList list = new ArrayList();
list.Add(1);
list.Add(2);
list.add("Hello");
list.Add(3.14);
```

Se puede acceder a los elementos de la lista mediante el índice:

```csharp
var first = list[0];
var last = list[list.Count - 1];
```

Como se puede ver en el ejemplo anterior el arrayList tiene un atributo Count
que indica el número de elementos que contiene.

Se puede iterar sobre los elementos de la lista mediante un bucle for:

```csharp
for (int i = 0; i < list.Count; i++)
{
    Console.WriteLine(list[i]);
}
```

o

```csharp
foreach (var item in list)
{
    Console.WriteLine(item);
}
```

Se pueden insertar elementos en una posición determinada:

```csharp
list.Insert(0, "First");
```

Se pueden eliminar elementos de la lista:

```csharp
list.RemoveAt(0);
```





