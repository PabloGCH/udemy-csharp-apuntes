INTERFACES
===================

Las interfaces son como un contrato que la clase debe cumplir.
Esta define los metodos y atributos que la clase debe tener.
La convencion de nombrado implica anteponer una I a la clase.

```csharp
public interface IAnimal
{
    string Nombre { get; set; }
    void Comer();
    void Dormir();
}
```

Y la clase que implementa la interfaz debe implementar todos los metodos y atributos de la interfaz.

```csharp
public class Perro : IAnimal
{
    public string Nombre { get; set; }

    public void Comer()
    {
        Console.WriteLine("El perro come");
    }

    public void Dormir()
    {
        Console.WriteLine("El perro duerme");
    }
}
```

Las clases solo pueden heredar de una clase, pero pueden implementar varias interfaces.

Interfaz IDisposable
--------------------

La interfaz IDisposable es una interfaz que define un metodo Dispose() que libera los recursos no administrados de la clase.

```csharp
public class MiClase : IDisposable
{
    public void Dispose()
    {
        // Liberar recursos no administrados
    }
}
```









