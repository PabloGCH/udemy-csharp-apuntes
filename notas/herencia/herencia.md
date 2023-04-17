Herencia
==============

En csharp se puede heredar de una clase, es decir, una clase puede heredar de otra clase.

Ejemplo:

```csharp
class Persona
{
    public string Nombre { get; set; }
    public string Apellido { get; set; }
    public int Edad { get; set; }
}
class Estudiante : Persona
{
    public string Carrera { get; set; }
    public int Semestre { get; set; }
}
```

En el ejemplo anterior, la clase `Estudiante` hereda de la clase `Persona`, por lo tanto, la clase `Estudiante` tiene los atributos de la clase `Persona` (Y metodos).


Polimorfismo
==============

En csharp, se puede sobreescribir un metodo de una clase padre, es decir, se puede sobreescribir un metodo de una clase padre en una clase hija.

Ejemplo:

```csharp
class animal
{
    public void comer()
    {
        Console.WriteLine("El animal esta comiendo");
    }
}
class perro : animal
{
    public void comer()
    {
        Console.WriteLine("El perro esta comiendo");
    }
}
```


Interfaces
==============

En csharp, se puede implementar una interfaz, es decir, una clase puede implementar una interfaz.
Esta sirve para que una clase tenga un comportamiento especifico.

Ejemplo:

```csharp
interface IAnimal
{
    int Patas { get; set; }
    void comer();
}
class perro : IAnimal
{
    public int Patas { get; set; }
    public void comer()
    {
        Console.WriteLine("El perro esta comiendo");
    }
}
```

En el ejemplo anterior, la clase `perro` implementa la interfaz `IAnimal`, por lo tanto, la clase `perro` tiene el comportamiento de la interfaz `IAnimal` (Y metodos).
En caso de no implementar todos los metodos y atributos de la interfaz el compilador arrojara un error.











