METODOS ANONIMOS
================

En csharp podemos crear metodos anonimos, estos son metodos que no tienen nombre y que se pueden asignar a una variable, a un delegado o pasarlos como parametro a otro metodo.


Ejemplo 1
---------

```csharp
delegate void MiDelegado(string msj);
class Program
{
    static void Main(string[] args)
    {
        MiDelegado delegado = delegate(string msj)
        {
            Console.WriteLine(msj);
        };
        delegado("Hola Mundo");
    }
}
```
