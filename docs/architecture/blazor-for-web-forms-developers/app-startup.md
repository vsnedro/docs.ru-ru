---
title: Запуск приложений
description: Узнайте, как определить логику запуска для приложения.
author: csharpfritz
ms.author: jefritz
ms.date: 02/25/2020
ms.openlocfilehash: 3d460750c36f64b8ad343755bd63b47af5c310d9
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87914884"
---
# <a name="app-startup"></a>Запуск приложений

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Приложения, написанные для ASP.NET, обычно имеют `global.asax.cs` файл, определяющий `Application_Start` событие, которое управляет тем, какие службы настроены и доступны как для отрисовки HTML, так и для обработки .NET. В этой главе рассматриваются некоторые различия с ASP.NET Core и сервером Блазор.

## <a name="application_start-and-web-forms"></a>Application_Start и веб-формы

По умолчанию метод веб-форм `Application_Start` увеличился в течение нескольких лет для решения многих задач настройки.  Новый проект Web Forms с шаблоном по умолчанию в Visual Studio 2019 теперь содержит следующую логику конфигурации:

- `RouteConfig`— Маршрутизация URL-адресов приложений
- `BundleConfig`— Объединение и минификации в CSS и JavaScript

Каждый из этих отдельных файлов находится в `App_Start` папке и запускается только один раз в начале приложения.  `RouteConfig`в шаблоне проекта по умолчанию добавляет `FriendlyUrlSettings` for Web Forms, чтобы разрешить URL-адресам приложений опустить `.ASPX` расширение файла.  Шаблон по умолчанию также содержит директиву, которая предоставляет постоянные коды состояния перенаправления HTTP (HTTP 301) для `.ASPX` страниц по понятному URL-адресу с именем файла, в котором пропущено расширение.

С помощью ASP.NET Core и Блазор эти методы упрощены и объединяются в `Startup` класс, или они устраняются в пользу общих веб-технологий.

## <a name="blazor-server-startup-structure"></a>Начальная структура сервера блазор

Серверные приложения блазор располагаются поверх приложения ASP.NET Core 3,0 или более поздней версии.  ASP.NET Core веб-приложения настраиваются с помощью пары методов класса в `Startup.cs` корневой папке приложения.  Содержимое класса Startup по умолчанию указано ниже

```csharp
public class Startup
{
  public Startup(IConfiguration configuration)
  {
    Configuration = configuration;
  }

  public IConfiguration Configuration { get; }

  // This method gets called by the runtime. Use this method to add services to the container.
  // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
  public void ConfigureServices(IServiceCollection services)
  {
    services.AddRazorPages();
    services.AddServerSideBlazor();
    services.AddSingleton<WeatherForecastService>();
  }

  // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
  public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
  {
    if (env.IsDevelopment())
    {
      app.UseDeveloperExceptionPage();
    }
    else
    {
      app.UseExceptionHandler("/Error");
      // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
      app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
      endpoints.MapBlazorHub();
      endpoints.MapFallbackToPage("/_Host");
   });
  }
 }
```

Как и в остальных ASP.NET Core, класс Startup создается с принципами внедрения зависимостей.  Объект `IConfiguration` предоставляется конструктору и скрыт в открытом свойстве для последующего доступа во время настройки.

`ConfigureServices`Метод, представленный в ASP.NET Core, позволяет настроить различные службы ASP.NET Core Framework для встроенного контейнера внедрения зависимостей платформы.  Различные `services.Add*` методы добавляют службы, которые включают такие функции, как проверка подлинности, Razor Pages, маршрутизация контроллера MVC, SignalR и взаимодействие с сервером блазор, между многими другими.  Этот метод не требовался в веб-формах, так как анализ и обработка файлов ASPX, ASCX, ASHX и ASMX была определена ссылкой на ASP.NET в файле конфигурации web.config.  Дополнительные сведения о внедрении зависимостей в ASP.NET Core доступны в [интерактивной документации](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).

`Configure`Метод вводит концепцию конвейера HTTP для ASP.NET Core.  В этом методе мы объявляем сверху вниз по [промежуточного слоя](middleware.md) , который будет выполнять все запросы, отправленные в наше приложение. Большинство этих функций в конфигурации по умолчанию были разбиты по файлам конфигурации веб-форм и теперь находятся в одном месте для простоты ссылок.

Больше не является конфигурацией настраиваемой страницы ошибок, помещенной в `web.config` файл, но теперь она настроена так, чтобы всегда отображалась, если среда приложения не помечена `Development` .  Кроме того, ASP.NET Core приложения настроены для обслуживания защищенных страниц с помощью TLS по умолчанию с помощью `UseHttpsRedirection` вызова метода.

Далее в указан непредвиденный метод конфигурации `UseStaticFiles` .  В ASP.NET Core поддержка запросов для статических файлов (таких как JavaScript, CSS и файлы изображений) должна быть явно включена, и по умолчанию общедоступными могут быть только файлы в папке *wwwroot* приложения.

Следующая строка является первой, которая реплицирует один из параметров конфигурации из веб-форм: `UseRouting` .  Этот метод добавляет маршрутизатор ASP.NET Core к конвейеру, который можно настроить здесь или в отдельных файлах, к которым может быть выполнена маршрутизация.  Дополнительные сведения о конфигурации маршрутизации см. в разделе « [Маршрутизация](pages-routing-layouts.md)».

Последняя инструкция в этом методе определяет конечные точки, которые ASP.NET Core прослушивает.  Это доступные в Интернете расположения, к которым можно получить доступ на веб-сервере и которые получают некоторое содержимое, обрабатываемое .NET и возвращенные вам.  Первая запись, `MapBlazorHub` настраивает концентратор SignalR для использования в режиме реального времени и постоянного подключения к серверу, где обрабатывается состояние и отрисовка компонентов блазор.  `MapFallbackToPage`Вызов метода указывает на веб-расположение страницы, которая запускает приложение блазор, а также настраивает приложение для обработки запросов на глубокую компоновку со стороны клиента.  Эта функция будет отображаться на рабочем месте, если открыть браузер и перейти непосредственно к Блазор обработанному маршруту в приложении, например `/counter` в шаблоне проекта по умолчанию. Запрос обрабатывается с помощью резервной страницы *_Host. cshtml* , которая затем запускает маршрутизатор блазор и визуализирует страницу счетчика.

## <a name="upgrading-the-bundleconfig-process"></a>Обновление процесса Бундлеконфиг

Технологии объединения таких ресурсов, как таблицы стилей CSS и файлы JavaScript, значительно развиваются благодаря другим технологиям, обеспечивающим быстрое развитие средств и методов управления этими ресурсами.  Для этого мы рекомендуем использовать средство командной строки узла, такое как grunt/gulp/веб-пакет, для упаковки статических ресурсов.

Программы командной строки grunt, gulp и веб-пакета и связанные с ними конфигурации могут быть добавлены в приложение, а ASP.NET Core будут без каких-либо игнорировать эти файлы в процессе сборки приложения.  Можно добавить вызов для выполнения своих задач, добавив `Target` внутри файла проекта синтаксис, аналогичный приведенному ниже, который запускает сценарий gulp и `min` целевой объект внутри этого скрипта.

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="gulp min" />
</Target>
```

Дополнительные сведения о обеих стратегиях управления файлами CSS и JavaScript можно найти в ASP.NET Core документации по [статическим ресурсам в пакете и уменьшение](https://docs.microsoft.com/aspnet/core/client-side/bundling-and-minification) .

>[!div class="step-by-step"]
>[Назад](project-structure.md)
>[Вперед](components.md)
