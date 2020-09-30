Vlix Http Server
================

**Vlix Http Server** is a simple and lightweight http server used to serve static file content. This means any directory on your PC can be turned into a web server to serve files such as 'html'. Even though it is lightweight Vlix Http Server is enterprise and production ready, as it supports:

- Multi threaded request processing.

- Content Caching

  

These features allow the Vlix Http Server to serve thousands of request with ease, without latency.

> The Vlix Http Server is part of **Vlix** (http://vlix.me). **Vlix** overall is an Industrial Data Platform which uses this Http Server to serve content from it's back end. 😃



Vlix Http Server targets the **DotNet Framework**, which lacks a dedicated web server like Kestrel for DotNet Core.



## Embedding it in your project

Install the [VlixHttpServer Package](https://www.nuget.org/packages/VlixHttpServer/) via Nuget:

```powershell
Install-Package VlixHttpServer
```

In your project, to create a Http Server simply use:

```c#
VlixHttpServer vlixHttpServer = new VlixHttpServer("C:\\YourDirectory\\Name",8080,true);
vlixHttpServer.Start();
```

You can catch also handle exceptions. Example:

```C#
VlixHttpServer vlixHttpServer = new VlixHttpServer(Environment.GetFolderPath(Environment.SpecialFolder.CommonApplicationData) + "\\Vlix\\SimpleHttpServer\\", 8080, true, (Ex) => 
            {
                string ExceptionString = Ex.ToString();
                SomeLogFunction(ExceptionString);
            });
            vlixHttpServer.Start();
```

To stop the server simply call

```C#
vlixHttpServer.Stop();
```

## Licence

MIT
