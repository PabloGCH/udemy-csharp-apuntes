Diccionarios
=============


Los diccionarios son estructuras de datos que nos permiten almacenar valores de la forma clave:valor.

En csharp los diccionarios se implementan con la clase Dictionary<TKey, TValue>.

Para crear un diccionario hacemos:

```csharp
Dictionary<string, int> diccionario = new Dictionary<string, int>();
```

Para añadir elementos al diccionario hacemos:

```csharp
diccionario.Add("uno", 1);
diccionario.Add("dos", 2);
diccionario.Add("tres", 3);
```

Para acceder a un elemento del diccionario hacemos:

```csharp
int valor = 0;
diccionario.tryGetValue("uno", out valor);
```

o

```csharp
int valor = diccionario["uno"];
```


Para recorrer el diccionario hacemos: 

```csharp
foreach (KeyValuePair<string, int> elemento in diccionario)
{
    Console.WriteLine("Clave: {0}, Valor: {1}", elemento.Key, elemento.Value);
}
```


Para eliminar un elemento del diccionario hacemos:

```csharp
diccionario.Remove("uno");
```


Para obtener las keys del diccionario hacemos:

```csharp
Dictionary<string, int>.KeyCollection keys = diccionario.Keys; //un array de strings (las keys)
```



