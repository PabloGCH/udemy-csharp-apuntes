Clases
=================

Las clases tienen una estructura:

```csharp
class NombreClase
// Cuerpo
//===============================
{
    // Constantes
    //-----------------------

    const int CONSTANT= 0;
    const IVA7 = 7, IVA10 = 10, IVA21 = 21;
    // Propiedades o campos
    //-----------------------

    public int Campo;
    public int Campo2 { get; set; }
    public int Campo3 { get; private set; }
    public readonly int Campo4;

    // Métodos
    //-----------------------
    public void Metodo(int valor) {
        Campo = valor;
    }
    public int Metodo2(int valor) {
        return valor + Campo;
    }
    public int Metodo3(int valor) => valor;
    public int Metodo4(int valor) {
        Metodo(valor);
        return Metodo2(valor);
    }
    // Eventos
    //-----------------------
    // Indizadores
    //-----------------------
    // Operadores
    //-----------------------
    // Constructores
    //-----------------------
    // Deconstructores
    //-----------------------
    // Tipos
    //-----------------------
}
```

Accesibilidad
-----------------------

* **public**: Accesible desde cualquier parte del código.
* **private**: Accesible sólo desde la clase.
* **protected**: Accesible desde la clase y sus clases derivadas.
* **internal**: Accesible desde el mismo ensamblado.
* **protected internal**: Accesible desde el mismo ensamblado y sus clases derivadas.

Clase Abstracta
-----------------------

Una clase abstracta es una clase que no se puede instanciar, pero que puede tener métodos abstractos. Los métodos abstractos no tienen implementación, y deben ser implementados en las clases derivadas.

```csharp
abstract class ClaseAbstracta
{
    public abstract void MetodoAbstracto(); // No tiene implementación y debe ser implementado en las clases derivadas.
}
```

Tambien puede tener métodos virtuales, que pueden ser sobreescritos en las clases derivadas.

```csharp
abstract class ClaseAbstracta
{
    public virtual void MetodoVirtual() { } // Puede ser sobreescrito en las clases derivadas.
}
```

Para sobreescribir un método virtual, se utiliza la palabra clave **override**.

```csharp
class ClaseDerivada : ClaseAbstracta
{
    public override void MetodoVirtual() { } // Sobreescritura del método virtual.
}
```

Clase Sellada
-----------------------

Una clase sellada es una clase que no puede ser heredada.

```csharp
sealed class ClaseSellada
{
}
```

Clase Estática
-----------------------

Una clase estática es una clase que no puede ser instanciada, y que sólo puede contener miembros estáticos.

```csharp   
static class ClaseEstatica
{
    public static int CampoEstatico;
    public static void MetodoEstatico() { }
}
```


Metodos de extension
-----------------------

Un método de extensión es un método que se puede invocar como si fuera un método de la clase a la que se extiende.

```csharp
public static class Extensiones
{
    public static int Sumar(this int valor, int valor2) {
        return valor + valor2;
    }
}
```

Para invocar el método de extensión, se utiliza la palabra clave **this**.

```csharp
int valor = 5;
int valor2 = 10;
int resultado = valor.Sumar(valor2);
```




