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


