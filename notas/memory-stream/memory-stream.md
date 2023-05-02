MEMORY STREAM
==============

Se instancia un objeto de tipo MemoryStream, el cual es un stream de memoria.

```csharp
MemoryStream ms = new MemoryStream();
```

Este tiene los atributos

```csharp
ms.Position; // Posicion actual del MemoryStream
ms.Length; // Longitud del MemoryStream
ms.Capacity; // Capacidad del MemoryStream
```

Los podemos posicionar en cualquier parte del MemoryStream con el metodo Seek

```csharp
ms.Seek(0, SeekOrigin.Begin); // Posiciona el MemoryStream en el inicio
ms.Seek(10. SeekOrigin.Begin); // Posiciona el MemoryStream en la posicion 10

ms.Seek(0, SeekOrigin.Current); // Posiciona el MemoryStream en la posicion actual
ms.Seek(10, SeekOrigin.Current); // Posiciona el MemoryStream en la posicion actual + 10
ms.Seek(-10, SeekOrigin.Current); // Posiciona el MemoryStream en la posicion actual - 10


ms.Seek(0, SeekOrigin.End); // Posiciona el MemoryStream en el final
ms.Seek(-10, SeekOrigin.End); // Posiciona el MemoryStream en el final - 10
```

Para leer el MemoryStream se utiliza el metodo Read

```csharp
byte[] buffer = new byte[ms.Length];
ms.Read(buffer, 0, buffer.Length); //Lee todo el MemoryStream
```




