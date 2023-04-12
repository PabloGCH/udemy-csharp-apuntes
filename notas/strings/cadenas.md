Cadenas de texto
================

Son el tipo 'string', otros tipos de datos pueden ser convertidos a cadenas de texto
con el metodo 'toString()'.

Ejemplos:

```csharp
string cadena = "Hola mundo";
string cadena2 = 1234.ToString();
```

Concatenacion de Cadenas
------------------------

Para concatenar cadenas de texto se utiliza el operador '+'

```csharp
string cadena = "Hola";
string cadena2 = "Mundo";
string cadena3 = cadena + ' ' + cadena2;
```

o el metodo 'Concat()'

```csharp
string cadena = "Hola";
string cadena2 = "Mundo";
string cadena3 = string.Concat(cadena, ' ', cadena2);
```

o se pueden insertar variables dentro de una cadena de texto

```csharp
string cadena = "Mundo";
string cadena3 = $"Hola {cadena}";
```

Operaciones con Cadenas
-----------------------

El tipo 'string' tiene varios metodos para realizar operaciones con cadenas de texto.
Como por ejemplo:

```csharp
string cadena = "Hola Mundo"; // cadena inicial
cadena = cadena.ToUpper(); // convierte la cadena a mayusculas
cadena = cadena.ToLower(); // convierte la cadena a minusculas
cadena = cadena.Trim(); // elimina los espacios en blanco al inicio y al final de la cadena
cadena = cadena.Replace("Hola", "Adios"); // reemplaza una cadena por otra
cadena = cadena.Substring(0, 4); // extrae una subcadena de la cadena
cadena = cadena.Insert(0, "Adios "); // inserta una cadena en la posicion indicada
cadena = cadena.Remove(0, 5); // elimina una subcadena de la cadena
cadena = cadena.Contains("Hola"); // verifica si la cadena contiene una subcadena
cadena = cadena.StartsWith("Hola"); // verifica si la cadena empieza con una subcadena
cadena = cadena.EndsWith("Mundo"); // verifica si la cadena termina con una subcadena
cadena = cadena.Equals("Hola Mundo"); // verifica si la cadena es igual a otra cadena
cadena = cadena.IndexOf("Mundo"); // devuelve la posicion de la subcadena dentro de la cadena
cadena = cadena.LastIndexOf("Mundo"); // devuelve la ultima posicion de la subcadena dentro de la cadena
cadena = cadena.Length; // devuelve la longitud de la cadena
cadena = cadena.Split(' '); // devuelve un arreglo de cadenas separadas por el caracter indicado
                            //Pueden ser caractares como espacios, comas, puntos, etc.
```


String Builder
--------------

Es una clase que permite concatenar cadenas de texto de forma mas eficiente que
con el operador '+' o el metodo 'Concat()'

```csharp
StringBuilder sb = new StringBuilder();
sb.Append("Hola");
sb.Append(" ");
sb.Append("Mundo");
string cadena = sb.ToString();
```

Tambien se puede agregar un salto de linea con el metodo 'AppendLine()'

```csharp
StringBuilder sb = new StringBuilder();
sb.AppendLine("Hola");
sb.AppendLine("Mundo");
string cadena = sb.ToString();
```

Formateo de fechas
------------------

El tipo 'DateTime' tiene varios metodos para formatear la fecha y hora.

ejemplo:

```csharp
DateTime fecha = new DataTime();
fecha = DateTime.Now;
string fechaFormateada = fecha.ToLocalTime()
fechaFormateada = fecha.ToLongDateString();
fechaFormateada = fecha.ToLongTimeString();
fechaFormateada = fecha.ToShortDateString();
fechaFormateada = fecha.ToShortTimeString();
fechaFormateada = fecha.ToString();
fechaFormateada = fecha.ToUniversalTime();
```





