ENTITY FRAMEWORK
================

SETUP
-----

Para utilizarlo sera necesario instalar el paquete NuGet EntityFrameworkCore.SqlServer y EntityFrameworkCore.Tools

PASOS IMPORTANTES

- Crear clase de contexto ContextDB que herede de DbContext
- Agregar

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<ContextDB>(options => 
            options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
}
```

al metodo ConfigureServices() en el archivo Startup.cs

- Agrego al archivo appsettings.json la cadena de conexion

```json
"ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=EFGetStarted.AspNetCore.NewDb;Trusted_Connection=True;MultipleActiveResultSets=true"
}
```

CREAR MODELO
------------

- Crear carpeta Models
- Creo por ejemplo clase Product

```csharp
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Price { get; set; }
}
```

- Agrego DbSet<Product> Products { get; set; } a la clase ContextDB

```csharp
public class ContextDB : DbContext
{
    public ContextDB(DbContextOptions<ContextDB> options) : base(options)
    {
    }

    public DbSet<Product> Products { get; set; }
}
```

- Y agregamos al metodo OnModelCreating() de la clase ContextDB

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.Entity<Product>().ToTable("Products");
}
```

- Realizamos la migracion con el comando

```bash
Add-Migration InitialCreate
```

- Y actualizamos la base de datos con el comando

```bash
Update-Database
```


INYECCION DE DEPENDENCIAS
-------------------------

- Creo una interfaz IContextDB

```csharp
public interface IContextDB
{
    DbSet<Product> Products { get; set; }
    Int SaveChanges();
    Task<Int> SaveChangesAsync(bool acceptAllChangesOnSuccess, CancellationToken cancellationToken = default(CancellationToken));
}
```

- Hacer que ContextDB implemente la interfaz IContextDB

```csharp
public class ContextDB : DbContext, IContextDB
{
    public ContextDB(DbContextOptions<ContextDB> options) : base(options)
    {
    }

    public DbSet<Product> Products { get; set; }
}
```

- Creo el servicio ProductService y su interfaz

```csharp
public class ProductService : IProductService
{

}
```


- Agrego al metodo ConfigureServices() en el archivo Startup.cs

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddTransient<IContextDB, ContextDB>();
    services.AddTransient<IProductService, ProductService>();


    services.AddDbContext<ContextDB>(options => 
            options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
}
```








