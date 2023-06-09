#LINQ
=============================

##INTRO
--------------

LINQ es una api para interactuar con diversas fuentes de datos usando un lenguaje de consultas similar a SQL.

Ejemplo:

```csharp
//USANDO EXPRESIONES LINQ
var query = from c in db.Customers
            where c.City == "London"
            select c;
```

Consultas con expresiones lambda:

```csharp
//USANDO EXPRESIONES LAMBDA
List<Libro> libros = Libro.GetLibros();
vat titulos = libros
    .Where(l => l.Paginas > 100)
    .Select(l => l.Titulo);
```

##CLASE DE RETORNO
--------------

Se puede usar la palabra reservada new para crear una clase de retorno anonima.

```csharp
List<Libro> libros = Libro.GetLibros();
var titulos = from l in libros
              where l.Paginas > 100
              select new { l.Titulo, l.Paginas };
```

```csharp
List<Libro> libros = Libro.GetLibros();
var titulos = libros
    .Where(l => l.Paginas > 100)
    .Select(l => new { l.Titulo, l.Paginas });
```



##CLAUSULAS
--------------

Las clausulas de una consulta LINQ son:

###FROM

La clausula FROM especifica la fuente de datos de la consulta. Puede ser una coleccion, un array, un objeto que implemente IEnumerable, un objeto que implemente IQueryable, un objeto que implemente IQueryProvider, un objeto que implemente IEnumerable<T> o un objeto que implemente IQueryable<T>.

```csharp
//USANDO EXPRESIONES LINQ
var query = from c in db.Customers
            where c.City == "London"
            select c;
```

```csharp
//USANDO EXPRESIONES LAMBDA
List<Libro> libros = Libro.GetLibros();
vat titulos = libros
    .Where(l => l.Paginas > 100)
    .Select(l => l.Titulo);
```

###JOIN

La clausula JOIN especifica la relacion entre dos fuentes de datos.

```csharp
//USANDO EXPRESIONES LINQ
List<Libro> libros = Libro.GetLibros();
List<LibroStock> stock = LibroStock.GetStock();

var titulos = from l in libros
              join s in stock on l.codigo equals s.codigo
              select l.Titulo;
```

```csharp
//USANDO EXPRESIONES LAMBDA
List<Libro> libros = Libro.GetLibros();
List<LibroStock> stock = LibroStock.GetStock();

var titulos = libros
    .Join(stock, l => l.codigo, s => s.codigo, (l, s) => l.Titulo);
```

###LET

La clausula LET permite definir variables que pueden ser usadas en la consulta.

```csharp
//USANDO EXPRESIONES LINQ
List<Libro> libros = Libro.GetLibros();
List<LibroStats> stats = LibroStats.GetStats();

var titulos = from l in libros
              join s in stats on l.codigo equals s.codigo
              let total = l.precio * s.ventas
              select new { l.Titulo, total };
```

```csharp
//USANDO EXPRESIONES LAMBDA
List<Libro> libros = Libro.GetLibros();
List<LibroStats> stats = LibroStats.GetStats();

var titulos = libros
    .Join(stats, l => l.codigo, s => s.codigo, (l, s) => new { l.Titulo, total = l.precio * s.ventas });
```

###WHERE

La clausula WHERE permite filtrar los datos de la consulta.

```csharp
//USANDO EXPRESIONES LINQ
List<Libro> libros = Libro.GetLibros();
List<LibroStats> stats = LibroStats.GetStats();
List<LibroStock> stock = LibroStock.GetStock();


var librosMasVendidosDisponibles = from l in libros
                                   join s in stats on l.codigo equals s.codigo
                                   join st in stock on l.codigo equals st.codigo
                                   where s.ventas > 100 && st.stock > 0
                                   select l.Titulo;
```

```csharp
//USANDO EXPRESIONES LAMBDA
List<Libro> libros = Libro.GetLibros();
List<LibroStats> stats = LibroStats.GetStats();
List<LibroStock> stock = LibroStock.GetStock();

var librosMasVendidosDisponibles = libros
    .Join(stats, l => l.codigo, s => s.codigo, (l, s) => new { l.Titulo, s.ventas })
    .Join(stock, l => l.codigo, st => st.codigo, (l, st) => new { l.Titulo, l.ventas, st.stock })
    .Where(l => l.ventas > 100 && l.stock > 0)
    .Select(l => l.Titulo);
```

Las clausulas WHERE pueden ser encadenadas.

```csharp
//USANDO EXPRESIONES LINQ
List<Libro> libros = Libro.GetLibros();
List<LibroStats> stats = LibroStats.GetStats();
List<LibroStock> stock = LibroStock.GetStock();

var librosMasVendidosDisponibles = from l in libros
                                   join s in stats on l.codigo equals s.codigo
                                   join st in stock on l.codigo equals st.codigo
                                   where s.ventas > 100
                                   where st.stock > 0
                                   select l.Titulo;
```

```csharp
//USANDO EXPRESIONES LAMBDA
List<Libro> libros = Libro.GetLibros();
List<LibroStats> stats = LibroStats.GetStats();
List<LibroStock> stock = LibroStock.GetStock();

var librosMasVendidosDisponibles = libros
    .Join(stats, l => l.codigo, s => s.codigo, (l, s) => new { l.Titulo, s.ventas })
    .Join(stock, l => l.codigo, st => st.codigo, (l, st) => new { l.Titulo, l.ventas, st.stock })
    .Where(l => l.ventas > 100)
    .Where(l => l.stock > 0)
    .Select(l => l.Titulo);
```

###ORDER BY

La clausula ORDER BY permite ordenar los datos de la consulta.

```csharp
//USANDO EXPRESIONES LINQ
List<Libro> libros = Libro.GetLibros();
list<LibroStats> stats = LibroStats.GetStats();

var librosMasVendidos = from l in libros
                        join s in stats on l.codigo equals s.codigo
                        orderby s.ventas descending
                        select l.Titulo;
```

```csharp
//USANDO EXPRESIONES LAMBDA
List<Libro> libros = Libro.GetLibros();
list<LibroStats> stats = LibroStats.GetStats();

var librosMasVendidos = libros
    .Join(stats, l => l.codigo, s => s.codigo, (l, s) => new { l.Titulo, s.ventas })
    .OrderByDescending(l => l.ventas)
    .Select(l => l.Titulo);
```

###SELECT

La clausula SELECT permite seleccionar los datos de la consulta.
Hay ejemplos de SELECT en las consultas anteriores.


###GROUP OrderBy

La clausula GROUP permite agrupar los datos de la consulta.

```csharp
//USANDO EXPRESIONES LINQ
List<Libro> libros = Libro.GetLibros();

var librosMasVendidos = from l in libros
                        group l by l.categoryId into g
                        select new { CategoryId = g.Key, Books = g };

```

```csharp
//USANDO EXPRESIONES LAMBDA
List<Libro> libros = Libro.GetLibros();

var librosMasVendidos = libros
    .GroupBy(l => l.categoryId)
    .Select(g => new { CategoryId = g.Key, Books = g });
```

##OPERADORES
--------------

###OPERADORES MATEMATICOS
```csharp
var count = libros.Count();
var sum = libros.Sum(l => l.precio);
var avg = libros.Average(l => l.precio);
var min = libros.Min(l => l.precio);
var max = libros.Max(l => l.precio);
```
###OPERADORES MIEMBRO
```csharp
var toma = libros.Take(10);
var salta = libros.Skip(10);
var saltaYtoma = libros.Skip(10).Take(10); //SIRVE PARA PAGINADO
var primero = libros.First();
var primeroOdefault = libros.FirstOrDefault();
var ultimo = libros.Last();
var single = libros.Single(l => l.codigo == 1);

var any = libros.Any(l => l.precio > 100); //retorna true si hay alguno
var all = libros.All(l => l.precio > 100); //retorna true si todos cumplen
var contains = libros.Contains(libro); //retorna true si el libro esta en la lista
```
































































