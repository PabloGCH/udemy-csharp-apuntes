NAMESPACE
=========

En csharp los namespaces son como carpetas, pero en vez de contener archivos, contienen clases. Los namespaces son una forma de organizar las clases y evitar conflictos de nombres. Por ejemplo, si dos clases tienen el mismo nombre, pero están en namespaces diferentes, no hay problema.
Para declarar un namespace, se usa la palabra clave `namespace` seguida del nombre del namespace. Por ejemplo:

```csharp
namespace MyNamespace
{
    // ...
}
```

Para usar un namespace, se usa la palabra clave `using` seguida del nombre del namespace. Por ejemplo:

```csharp
using MyNamespace;
```

Para usar un namespace dentro de otro namespace, se usa la palabra clave `using` seguida del nombre del namespace y el nombre del namespace padre separados por un punto. Por ejemplo:

```csharp
using MyNamespace.MySubNamespace;
```

Para declarar un namespace dentro de otro namespace, se usa la palabra clave `namespace` seguida del nombre del namespace y el nombre del namespace padre separados por un punto. Por ejemplo:

```csharp 
namespace MyNamespace.MySubNamespace
{
    // ...
}
```













