#Cambio de tipo
======================

Los cambios de tipo en csharp se pueden realizar de las siguientes formas:

## Casting explícito

Este tipo de casting se realiza cuando se quiere cambiar el tipo de una variable a otro tipo de variable que no es compatible con el tipo de la variable original.
Se realiza de la siguiente forma:

```csharp
int a = 10;
double b = (double)a;
```

## Casting implícito

Este tipo se da automaticamente al momento de asignar un valor a una variable, por ejemplo:

```csharp
int a = 10;
double b = a;
```

## Con clases de asistentes

En este caso se utiliza la clase Convert para realizar el cambio de tipo, por ejemplo:

```csharp
int a = 10;
double b = Convert.ToDouble(a);
```
