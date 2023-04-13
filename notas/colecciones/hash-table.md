Hash Table
=========

Un hash table es una estructura de datos que permite almacenar pares clave-valor. La clave es un identificador único que se utiliza para acceder al valor asociado. La clave puede ser de cualquier tipo, pero el valor debe ser un objeto. El tipo de la clave se especifica como el tipo de la clave del hash table, y el tipo de los valores se especifica como el tipo de los valores del hash table.

Ejemplo:

```csharp
var hashTable = new Hashtable();
hashTable.Add("key", "value");
hashTable.Add("key2", 123);
hashTable.Add("key3", new object());
```


Se puede acceder a los valores del hash table utilizando la clave:

```csharp
var value = hashTable["key"];
```

Para eliminar un elemento del hash table se utiliza el método Remove:

```csharp
hashTable.Remove("key");
```

Para comprobar si un elemento existe en el hash table se utiliza el método ContainsValue:

```csharp
if (hashTable.ContainsValue("value"))
{
    // ...
}
```

Puede comprobar si un key existe en el hash table utilizando el método ContainsKey:

```csharp
if (hashTable.ContainsKey("key"))
{
    // ...
}
```



