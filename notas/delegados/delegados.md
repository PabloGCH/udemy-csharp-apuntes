DELEGADOS
=========

Vienen de la clase delegate.
Se declaran con la palabra clave delegate.

```csharp
public delegate void Del(string msg);
```

Y se instancian:

```csharp
Del handler = DelegateMethod;
```

Sirve para pasar métodos como parámetros. (callback)

```csharp
public delegate void Del(string msg);
class Program
{
    Del handler = DelegateMethod;
    public static void DelegateMethod(string message)
    {
        System.Console.WriteLine(message);
    }
    public static void Main()
    {
        Del handler = DelegateMethod;
        MethodWithCallback(1, 2, handler);
    }
    public MethodWithCallback(int param1, int param2, Del callback)
    {
        callback("The number is: " + (param1 + param2).ToString());
    }
}
```




















