Metodos
======================

## Paso de parametros por valor y por referencia

### Paso de parametros por valor

```csharp
public void Sumar(int a, int b)
{
    a = a + b;
}
```

### Paso de parametros por referencia

```csharp
public void Sumar(ref int a, int b)
{
    a = a + b;
}
```
