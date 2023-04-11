Existen 2 valores diferentes a los usuales
============================================

Nulo
---------------
Ejemplo:

```csharp
string hola = null;

int altura = null;
```

Pero es necesario indicar que es nullable:

```csharp
int? altura = null;
```

Default
------------------

En este caso es 0

```csharp
int num = Default(int) //En este caso es 0
bool verdadero = Default(bool) //En este caso es false
```

