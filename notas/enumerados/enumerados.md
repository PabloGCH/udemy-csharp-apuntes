ENUMERADOS
==========

En csharp los enumerados son un tipo de dato que nos permite definir un conjunto de constantes con nombre, a las que se les asigna un valor entero por defecto.

Los enumerados se definen mediante la palabra clave enum, seguida del nombre del enumerado y entre llaves, los nombres de las constantes que lo componen.

```csharp
enum DiasSemana
{
    Lunes,
    Martes,
    Miercoles,
    Jueves,
    Viernes,
    Sabado,
    Domingo
}
```

Se accede a los elementos de un enumerado mediante el nombre del enumerado seguido de un punto y el nombre de la constante.

```csharp
DiasSemana dia = DiasSemana.Lunes;
```


Tambien podemos asignar un tipo de dato a los enumerados.

```csharp
enum DiasSemana : int
{
    Lunes,
    Martes,
    Miercoles,
    Jueves,
    Viernes,
    Sabado,
    Domingo
}
```


Se pueden castear a otros tipos de datos.

```csharp
int dia = (int)DiasSemana.Lunes; // 0
string dia = DiasSemana.Lunes.ToString(); // "Lunes"
```

