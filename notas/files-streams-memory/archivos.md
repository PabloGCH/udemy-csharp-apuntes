ARCHIVOS
========

En csharp manipulamos archivos con la clase FileStream, que se encuentra en el namespace System.IO.

```csharp
using System.IO;
//MODOS
// FileMode.Append (Si el archivo existe, se escribe al final)
// FileMode.Create (Crea un nuevo archivo si no existe, si existe lo sobreescribe)
// FileMode.CreateNew (Crea un nuevo archivo si no existe, si existe lanza una excepción)
// FileMode.Open (Abre un archivo existente, si no existe lanza una excepción)
// FileMode.OpenOrCreate (Abre un archivo existente, si no existe lo crea)
// FileMode.Truncate (Abre un archivo existente y lo trunca, si no existe lanza una excepción)

FileStream fs = new FileStream("archivo.txt", FileMode.Create);
```

Para escribir en el archivo, usamos el método Write de la clase FileStream.

```csharp
string cadena = "Hola mundo";
fs.Write(ASCIIEncoding.ASCII.GetBytes(cadena), 0, cadena.Length);
fs.Close();
```

Para leer el archivo, usamos el método Read de la clase FileStream.

```csharp
byte[] buffer = new byte[1024];
FileStream fs = new FileStream("archivo.txt", FileMode.Open);
fs.Read(buffer, 0, 1024);
fs.Close();
```








