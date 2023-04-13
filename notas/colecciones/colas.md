Colas
=========================

Una cola es una estructura de datos que permite almacenar elementos de forma ordenada. Los elementos se insertan en una cola por un extremo y se eliminan por el otro. La operación de inserción se denomina encolar y la operación de eliminación se denomina desencolar. Una cola es un tipo de estructura de datos abstracta, es decir, es una forma de representar los datos que permite definir operaciones sobre los mismos sin necesidad de especificar su representación interna.


Ejemplo:

```csharp
Queue cola = new Queue();
```

Se puede agregar un elemento a la cola con el método Enqueue:

```csharp
cola.Enqueue(1);
```

Se puede eliminar un elemento de la cola con el método Dequeue:

```csharp
cola.Dequeue();
```

Se puede obtener el primer elemento de la cola sin eliminarlo con el método Peek:

```csharp
cola.Peek();
```

Se puede ver si un elemento está en la cola con el método Contains:

```csharp 
cola.Contains(1);
```

Se puede vaciar la cola con el método Clear:

```csharp
cola.Clear();
```

Se puede obtener el número de elementos de la cola con la propiedad Count:

```csharp
cola.Count;
```






