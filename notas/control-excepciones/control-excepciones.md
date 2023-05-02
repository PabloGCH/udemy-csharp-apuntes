CONTROL DE EXCEPCIONES
======================

En csharp para controlar las excepciones se utiliza el bloque try-catch-finally.

```csharp
try
{
    // Código que puede generar una excepción
}
catch (Exception ex)
{
    // Código que se ejecuta cuando se genera una excepción
}
finally
{
    // Código que se ejecuta siempre
}
```

Los catch pueden ser encadenados para controlar diferentes tipos de excepciones.

```csharp
try
{
    // Código que puede generar una excepción
}
catch (DivideByZeroException ex)
{
    // Código que se ejecuta cuando se genera una excepción de tipo DivideByZeroException
}
catch (Exception ex)
{
    // Código que se ejecuta cuando se genera una excepción de tipo Exception
}
```

El mensaje de la excepción se puede obtener a través de la propiedad Message.

```csharp
try
{
    // Código que puede generar una excepción
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

Para crear una custom exception se debe heredar de la clase Exception.

```csharp
public class CustomException : Exception
{
    public CustomException() : base("Custom exception")
    {
    }
}
```

Y para lanzarla se utiliza la palabra reservada throw.

```csharp
throw new CustomException();
```


















