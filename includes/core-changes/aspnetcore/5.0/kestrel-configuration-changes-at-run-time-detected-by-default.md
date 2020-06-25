---
ms.openlocfilehash: d00b8ecaa61b358e062d85a2b68ca8a95cada442
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803239"
---
### <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a><span data-ttu-id="afc27-101">Kestrel. Обнаружение изменений конфигурации во время выполнения включено по умолчанию</span><span class="sxs-lookup"><span data-stu-id="afc27-101">Kestrel: Configuration changes at run time detected by default</span></span>

<span data-ttu-id="afc27-102">Kestrel теперь реагирует на изменения, внесенные в раздел `Kestrel` экземпляра `IConfiguration` проекта (например, *appsettings.json*) во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="afc27-102">Kestrel now reacts to changes made to the `Kestrel` section of the project's `IConfiguration` instance (for example, *appsettings.json*) at run time.</span></span> <span data-ttu-id="afc27-103">Дополнительные сведения о настройке Kestrel с помощью *appsettings.json* см. в примере *appsettings.json* в [конфигурации конечной точки](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span><span class="sxs-lookup"><span data-stu-id="afc27-103">To learn more about how to configure Kestrel using *appsettings.json*, see the *appsettings.json* example in [Endpoint configuration](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span></span>

<span data-ttu-id="afc27-104">Kestrel привязывает, отменяет привязку и повторно привязывает конечные точки при необходимости для реагирования на соответствующие изменения в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="afc27-104">Kestrel will bind, unbind, and rebind endpoints as necessary to react to these configuration changes.</span></span>

<span data-ttu-id="afc27-105">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span><span class="sxs-lookup"><span data-stu-id="afc27-105">For discussion, see issue [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="afc27-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="afc27-106">Version introduced</span></span>

<span data-ttu-id="afc27-107">5.0 (предварительная версия 7)</span><span class="sxs-lookup"><span data-stu-id="afc27-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="afc27-108">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="afc27-108">Old behavior</span></span>

<span data-ttu-id="afc27-109">До ASP.NET Core 5.0 (предварительная версия 6) Kestrel не поддерживал изменение конфигурации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="afc27-109">Before ASP.NET Core 5.0 Preview 6, Kestrel didn't support changing configuration at run time.</span></span>

<span data-ttu-id="afc27-110">В ASP.NET Core 5.0 (предварительная версия 6) можно было выбрать поведение по умолчанию для действий, выполняемых в настоящее время, для реагирования на изменения в конфигурации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="afc27-110">In ASP.NET Core 5.0 Preview 6, you could opt into the now-default behavior of reacting to configuration changes at run time.</span></span> <span data-ttu-id="afc27-111">Включение в конфигурацию требуемой привязки Kestrel вручную:</span><span class="sxs-lookup"><span data-stu-id="afc27-111">Opting in required binding Kestrel's configuration manually:</span></span>

```csharp
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.Hosting;

public class Program
{
    public static void Main(string[] args) =>
        CreateHostBuilder(args).Build().Run();

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                {
                    kestrelOptions.Configure(
                        builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: true);
                });

                webBuilder.UseStartup<Startup>();
            });
}
```

#### <a name="new-behavior"></a><span data-ttu-id="afc27-112">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="afc27-112">New behavior</span></span>

<span data-ttu-id="afc27-113">По умолчанию Kestrel реагирует на изменения конфигурации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="afc27-113">Kestrel reacts to configuration changes at run time by default.</span></span> <span data-ttu-id="afc27-114">Для поддержки этого изменения <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> по умолчанию вызывает `KestrelServerOptions.Configure(IConfiguration, bool)` с `reloadOnChange: true`.</span><span class="sxs-lookup"><span data-stu-id="afc27-114">To support that change, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> calls `KestrelServerOptions.Configure(IConfiguration, bool)` with `reloadOnChange: true` by default.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="afc27-115">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="afc27-115">Reason for change</span></span>

<span data-ttu-id="afc27-116">Было внесено изменение для поддержки перенастройки конечной точки во время выполнения без полного перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="afc27-116">The change was made to support endpoint reconfiguration at run time without completely restarting the server.</span></span> <span data-ttu-id="afc27-117">В отличие от полного перезапуска сервера, привязка неизмененных конечных точек не отменяется даже временно.</span><span class="sxs-lookup"><span data-stu-id="afc27-117">Unlike with a full server restart, unchanged endpoints aren't unbound even temporarily.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="afc27-118">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="afc27-118">Recommended action</span></span>

* <span data-ttu-id="afc27-119">В большинстве сценариев, в которых раздел конфигурации Kestrel по умолчанию не изменяется во время выполнения, это изменение не оказывает влияния и никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="afc27-119">For most scenarios in which Kestrel's default configuration section doesn't change at run time, this change has no impact and no action is needed.</span></span>
* <span data-ttu-id="afc27-120">Для сценариев, в которых раздел конфигурации Kestrel по умолчанию изменяется во время выполнения и Kestrel должен реагировать на него, это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afc27-120">For scenarios in which Kestrel's default configuration section does change at run time and Kestrel should react to it, this is now the default behavior.</span></span>
* <span data-ttu-id="afc27-121">Для сценариев, в которых раздел конфигурации Kestrel по умолчанию изменяется во время выполнения и Kestrel не должен реагировать на него, можно отказаться от приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="afc27-121">For scenarios in which Kestrel's default configuration section changes at run time and Kestrel shouldn't react to it, you can opt out as follows:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                    {
                        kestrelOptions.Configure(
                            builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: false);
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="afc27-122">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="afc27-122">**Notes:**</span></span>

<span data-ttu-id="afc27-123">Это изменение не изменяет поведение перегрузки `KestrelServerOptions.Configure(IConfiguration)`, которое по умолчанию по-прежнему `reloadOnChange: false`.</span><span class="sxs-lookup"><span data-stu-id="afc27-123">This change doesn't modify the behavior of the `KestrelServerOptions.Configure(IConfiguration)` overload, which still defaults to the `reloadOnChange: false` behavior.</span></span>

<span data-ttu-id="afc27-124">Также важно убедиться, что источник конфигурации поддерживает перезагрузку.</span><span class="sxs-lookup"><span data-stu-id="afc27-124">It's also important to make sure the configuration source supports reloading.</span></span> <span data-ttu-id="afc27-125">Для источников JSON перезагрузка настраивается путем вызова `AddJsonFile(path, reloadOnChange: true)`.</span><span class="sxs-lookup"><span data-stu-id="afc27-125">For JSON sources, reloading is configured by calling `AddJsonFile(path, reloadOnChange: true)`.</span></span> <span data-ttu-id="afc27-126">Для *appsettings.json* и *appsettings.{Environment}.json* повторная загрузка уже настроена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afc27-126">Reloading is already configured by default for *appsettings.json* and *appsettings.{Environment}.json*.</span></span>

#### <a name="category"></a><span data-ttu-id="afc27-127">Категория</span><span class="sxs-lookup"><span data-stu-id="afc27-127">Category</span></span>

<span data-ttu-id="afc27-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="afc27-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="afc27-129">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="afc27-129">Affected APIs</span></span>

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
