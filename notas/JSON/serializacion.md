SERIALIZACION DE JSON
=====================

En csharp se puede serializar un objeto a json de la siguiente manera:

```csharp
using System;
using Newtonsoft.Json;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            Class1 class1 = new Class1();
            class1.Name = "Juan";
            class1.Age = 20;
            var json = JsonConvert.SerializeObject(class1);
            Console.WriteLine(json);
            Class1 class2 = JsonConvert.DeserializeObject<Class1>(json);
            Console.WriteLine(class2.Name);
        }


        public class Class1
        {
            public string Name { get; set; }
            public int Age { get; set; }
        }
    }
}
```
