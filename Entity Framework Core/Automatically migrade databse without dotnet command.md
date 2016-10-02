On my ASP.NET Core application i needed to automatically run the
migrations on application startup. There is place in Program.cs 
that allows such action.

```csharp
public static void Main(string[] args)
{
    var host = new WebHostBuilder()
        .UseKestrel()
        .UseContentRoot(Directory.GetCurrentDirectory())
        .UseIISIntegration()
        .UseStartup<Startup>()
        .Build();
 
    // Migrate Database
    var services = (IServiceScopeFactory)host.Services.GetService(typeof(IServiceScopeFactory));
    using (var scope = services.CreateScope())
    {
        var db = scope.ServiceProvider.GetRequiredService<DbContext>();
        db.Database.Migrate();
    }

    host.Run();
}
```