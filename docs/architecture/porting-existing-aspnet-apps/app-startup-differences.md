---
title: Различия в запуске приложений между ASP.NET MVC и ASP.NET Core
description: ASP.NET MVC и ASP.NET Core значительно различаются в процессе запуска приложений. Узнайте о важных различиях и способах перехода с ASP.NET MVC на ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: eaf8d8fac42ddebbb944273b672666e0bd2b1a67
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401823"
---
# <a name="app-startup-differences-between-aspnet-mvc-and-aspnet-core"></a>Различия в запуске приложений между ASP.NET MVC и ASP.NET Core

ASP.NET приложения MVC, существовавшие полностью в Internet Information Server (IIS), это основной веб-сервер, доступный в операционных системах Windows. В отличие от ASP.NET MVC, ASP.NET Core приложения являются исполняемыми приложениями. Их можно запустить из командной строки с помощью `dotnet run` . Они имеют метод точки входа, например все программы на языке C#, обычно `public static void Main()` или аналогичные вариации (возможно, с аргументами или `async` поддержкой). Это, вероятно, наибольшее различие в архитектуре между ASP.NET Core и ASP.NET MVC и является одним из нескольких отличий, которые позволяют ASP.NET Core работать в системах, отличных от Windows.

## <a name="aspnet-mvc-startup"></a>Запуск ASP.NET MVC

Приложения ASP.NET, размещенные в службах IIS, используют службы IIS для создания экземпляров определенных объектов и вызова определенных методов при поступлении запроса. ASP.NET создает экземпляр класса *Global. asax* , который является производным от `HttpApplication` . При получении первого запроса перед обработкой запроса ASP.NET вызывает `Application_Start` метод в классе файла *Global. asax* . Любая логика, которая должна выполняться при запуске приложения ASP.NET MVC, может быть добавлена в этот метод.

Многие пакеты NuGet для ASP.NET MVC и Web API используют пакет веб- [активатора](https://github.com/davidebbo/WebActivator) , чтобы позволить им выполнять некоторый код во время запуска приложения. По соглашению этот код обычно добавляется в папку *App_Start* и настраивается с помощью атрибута для запуска непосредственно до или сразу после `Application_Start` .

Также можно использовать [открытый веб-интерфейс для .NET (OWIN) и Project Katana с ASP.NET MVC](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana). При этом приложение будет включать файл *Startup.CS* , который отвечает за настройку по промежуточного слоя запроса, что очень похоже на то, как работает ASP.NET Core.

Если необходимо выполнить код при запуске приложения ASP.NET MVC, обычно используется один из этих подходов.

## <a name="aspnet-core-startup"></a>Запуск ASP.NET Core

Как отмечалось ранее, ASP.NET Core приложения являются автономными программами. Таким образом, обычно они включают файл *Program.CS* , содержащий точку входа для приложения. Типичный пример этого файла приведен на рис. 2-1.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

**Рис. 2-1**. Типичный файл ASP.NET Core *Program.CS* .

Код, показанный на рисунке 2-1, создает *узел* для приложения, выполняет его сборку и выполняет. ASP.NET Core приложение выполняется на узле, настроенном указанным на `IHostBuilder` рисунке. Хотя можно полностью настроить ASP.NET Core приложение с помощью `IHostBuilder` , обычно основная часть этой работы выполняется в `Startup` классе.

`Startup`Класс предоставляет два метода для узла: `ConfigureServices` и `Configure` . `ConfigureServices`Метод используется для определения служб, которые будут использоваться приложением, и их времени существования. `Configure`Метод используется для определения того, как будет обрабатываться каждый запрос к приложению путем настройки конвейера запросов, состоящего из по промежуточного слоя.

В дополнение к коду, связанному с настройкой служб или конвейера запросов приложения, приложения могут иметь другой код, который должен выполняться при запуске приложения. Такой код обычно размещается в *Program.CS* или регистрируется как `IHostedService` , который будет запускаться [универсальным узлом](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1) при запуске приложения.

`IHostedService`Интерфейс просто предоставляет два метода: `StartAsync` и `StopAsync` . Вы регистрируете интерфейс в `ConfigureServices` , и узел выполняет остальные действия, вызывая `StartAsync` метод перед запуском приложения.

## <a name="porting-considerations"></a>Рекомендации по переносу

Группы, которым требуется перенести свои приложения из ASP.NET MVC в ASP.NET Core необходимо определить, какой код выполняется при запуске приложения, и определить соответствующее расположение для такого кода в своем ASP.NET Core приложении. Для пользовательского кода, необходимого для запуска при запуске приложения, особенно асинхронного кода, рекомендуемый подход обычно заключается в помещении этого кода в `IHostedService` реализации.

## <a name="references"></a>Ссылки

- [Общие сведения о жизненном цикле приложения ASP.NET для IIS 7](/previous-versions/aspnet/bb470252(v=vs.100))
- [Общие сведения о жизненном цикле приложения ASP.NET для IIS 5 и 6](/previous-versions/aspnet/ms178473(v=vs.100))
- [Начало работы с OWIN и Katana](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana)
- [Активатор](https://github.com/davidebbo/WebActivator)
- [Запуск приложения в ASP.NET Core](/aspnet/core/fundamentals/startup?preserve-view=true&view=aspnetcore-3.1)
- [Универсальный узел .NET в ASP.NET Core](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1)
- [IHostedService](../microservices/multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md)

>[!div class="step-by-step"]
>[Назад](architectural-differences.md)
>[Вперед](hosting-differences.md)
