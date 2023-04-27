BOXING
============


En csharp boxing es el proceso de convertir una variable de tipo valor a una variable de tipo referencia.

Ejemplo:

```csharp
int i = 123;
object o = i; // boxing
```

- El boxing copia el valor asi que si cambiamos el valor de i no afecta a o




UNBOXING
============

En csharp unboxing es el proceso de convertir una variable de tipo referencia a una variable de tipo valor.

Ejemplo:

```csharp
int i = 123;
object o = i; // BOXING
int j = (int)o; // UNBOXING
```
