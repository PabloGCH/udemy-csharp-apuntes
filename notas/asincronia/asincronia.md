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












