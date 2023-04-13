Programacion Orientada a Objetos
===============================

Clases
------

Se declaran:

```csharp
class NombreClase
{
    // Atributos
    // Metodos
}
```

Encapsulamiento
---------------

Se puede definir el nivel de acceso a los atributos y metodos de una clase.

```csharp
class NombreClase
{
    // Atributos
    private int atributoPrivado;
    public int atributoPublico;
    protected int atributoProtegido;
    internal int atributoInterno;
    protected internal int atributoProtegidoInterno;
    private protected int atributoPrivadoProtegido;
    // Metodos
    private void metodoPrivado() { }
    public void metodoPublico() { }
    protected void metodoProtegido() { }
    internal void metodoInterno() { }
    protected internal void metodoProtegidoInterno() { }
    private protected void metodoPrivadoProtegido() { }
}
```

Datos abstractos
----------------

Para poder utilizar las clases en otros archivos es necesario importarlas.

```csharp
using Personas; // Importa la clase Persona
Persona p = new Persona();
```













