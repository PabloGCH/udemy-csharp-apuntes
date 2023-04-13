Pila
=====================

Una pila es una estructura de datos que permite almacenar y recuperar datos en un orden LIFO (Last In First Out, último en entrar, primero en salir). Es decir, el último elemento que se introduce en la pila es el primero en ser recuperado.

Ejemplo:

```csharp
Stack pila = new Stack();
pila.Push(1);
pila.Push(2);
pila.Push(3);
```

Se puede limpia la pila con el método Clear:

```csharp
pila.Clear();
```

Se puede eliminar el último elemento de la pila con el método Pop:

```csharp
pila.Pop();
```

Se puede conseguir el tamaño de la pila con el método Count:

```csharp
pila.Count();
```
