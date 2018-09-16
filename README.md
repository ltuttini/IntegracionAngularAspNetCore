# Integracion Angular con Asp.Net Core

Los videos del meetup se encuentran publicados en youtube

[Angular - Introduccion](https://www.youtube.com/watch?v=3RZgZ1rqRaU "Angular - Introduccion")
[Integrando Angular con Asp.net Core](https://www.youtube.com/watch?v=-5hJg0lRmfo "Integrando Angular con Asp.net Core")

Como prerequisito se debe tener instalado node.js

Para ejecutar los ejemplos descargue el zip y en la linea de comando sobre la carpeta ejecutar:

`npm run install`

luego que termine de instalar los modulos ejecutar

`npm run dev-local`

la aplicacion se hostea bajo la url: http://localhost:4200

Para ejecutar el codigo asp.net core descargar el zip y abrir con Visual Studio 2017. Revisar el connection string definido en el archivo appsettings.json, la ejecucion creara la base de datos aplciando migration gracias a las lineas:

```csharp
 using (var serviceScope = app.ApplicationServices
                                                .GetRequiredService<IServiceScopeFactory>()
                                                .CreateScope())
{
     var context = serviceScope.ServiceProvider.GetService<ComicStoreContext>();
     context.Database.Migrate();
     context.SeedData();
 }

```
que se encuentran en el `Startup.cs`



