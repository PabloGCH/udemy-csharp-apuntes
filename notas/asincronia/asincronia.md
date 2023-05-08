ASINCRONIA
==========

Digamos que tenemos la funcion:

```csharp

public void GetAlgo() {
    Algo algo = new Algo();
    return algo;
}

```

Para hacer que la funcion sea asincrona, debemos agregar la palabra reservada `async` al metodo y cambiar el tipo de retorno a `Task<T>` donde `T` es el tipo de dato que retorna la funcion.

```csharp
public async Task<Algo> GetAlgo() {
    Algo algo = new Algo();
    return algo;
}
```

Ahora, para llamar a la funcion, debemos agregar la palabra reservada `await` antes de la llamada a la funcion.

```csharp
static async main() {
    Algo algo = await GetAlgo();
}
```

Tareas compuestas
-----------------

Digamos que tenemos las funciones:

```csharp
public void GetAlgo() {
    Algo algo = new Algo();
    return algo;
}
public void GetOtroAlgo() {
    OtroAlgo otroAlgo = new OtroAlgo();
    return otroAlgo;
}
```

Y queremos ejecutar un bloque de codigo cuando ambas funciones terminen. Para esto, podemos usar la funcion `Task.WhenAll`:

```csharp
static async Task main() {
    Task<Algo> algoTask = GetAlgo();
    Task<OtroAlgo> otroAlgoTask = GetOtroAlgo();
    await Task.WhenAll(algoTask, otroAlgoTask);
    Console.WriteLine("Ambas tareas terminaron");
}
```

Tambien existen los metodos:

- `Task.WhenAny`: Ejecuta un bloque de codigo cuando una de las tareas termina.














