EVENTOS
============

En csharp los eventos se declaran con el keyword event de la siguiente manera:

```csharp
class Program
{
    static void Main(string[] args)
    {
        //Se subscribe al evento
        Event e = New Event();
        e.evento += test; //Se ejecuta el metodo test cuando se dispare el evento
        e.evento += new Event.EventHandler(test); //Otra forma de subscribirse al evento
        

        //Se dispara el evento
        e.OnEvento("Hola");
    }

    public class Event
    {
        public delegate void EventHandler(string s);
        public event EventHandler evento;
    }

    public static void test(string s)
    {
        Console.WriteLine(s);
    }

    public void OnEvento(string s)
    {
        if (evento != null)
        {
            //Dispara el evento
            evento(s);
        }
    }
}
```
