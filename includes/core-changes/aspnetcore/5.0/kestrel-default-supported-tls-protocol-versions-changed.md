---
ms.openlocfilehash: 3244a36808fb687663241e704d08775ea5c96720
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803240"
---
### <a name="kestrel-default-supported-tls-protocol-versions-changed"></a><span data-ttu-id="34eb0-101">Kestrel. Изменены поддерживаемые версии протокола TLS по умолчанию</span><span class="sxs-lookup"><span data-stu-id="34eb0-101">Kestrel: Default supported TLS protocol versions changed</span></span>

<span data-ttu-id="34eb0-102">В Kestrel теперь используются стандартные версии протокола TLS, а не ограничивается лишь протоколами TLS 1.1 и TLS 1.2, как это было ранее.</span><span class="sxs-lookup"><span data-stu-id="34eb0-102">Kestrel now uses the system default TLS protocol versions rather than restricting connections to the TLS 1.1 and TLS 1.2 protocols like it did previously.</span></span>

<span data-ttu-id="34eb0-103">Это изменение позволяет:</span><span class="sxs-lookup"><span data-stu-id="34eb0-103">This change allows:</span></span>

* <span data-ttu-id="34eb0-104">использовать протокол TLS 1.3 по умолчанию в средах, поддерживающих его;</span><span class="sxs-lookup"><span data-stu-id="34eb0-104">TLS 1.3 to be used by default in environments that support it.</span></span>
* <span data-ttu-id="34eb0-105">использовать TLS 1.0 в некоторых средах (например, в Windows Server 2016 по умолчанию), в которых делать это обычно [нежелательно](/security/engineering/solving-tls1-problem).</span><span class="sxs-lookup"><span data-stu-id="34eb0-105">TLS 1.0 to be used in some environments (such as Windows Server 2016 by default), which is usually [not desirable](/security/engineering/solving-tls1-problem).</span></span>

<span data-ttu-id="34eb0-106">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span><span class="sxs-lookup"><span data-stu-id="34eb0-106">For discussion, see issue [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="34eb0-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="34eb0-107">Version introduced</span></span>

<span data-ttu-id="34eb0-108">5.0, предварительная версия 6</span><span class="sxs-lookup"><span data-stu-id="34eb0-108">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="34eb0-109">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="34eb0-109">Old behavior</span></span>

<span data-ttu-id="34eb0-110">Kestrel требовалось, чтобы для подключений по умолчанию использовался TLS 1.1 или TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="34eb0-110">Kestrel required that connections use TLS 1.1 or TLS 1.2 by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="34eb0-111">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="34eb0-111">New behavior</span></span>

<span data-ttu-id="34eb0-112">Kestrel позволяет операционной системе выбрать наилучший протокол для использования и блокирования небезопасных протоколов.</span><span class="sxs-lookup"><span data-stu-id="34eb0-112">Kestrel allows the operating system to choose the best protocol to use and to block insecure protocols.</span></span> <span data-ttu-id="34eb0-113"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> теперь по умолчанию использует `SslProtocols.None` вместо `SslProtocols.Tls12 | SslProtocols.Tls11`.</span><span class="sxs-lookup"><span data-stu-id="34eb0-113"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> now defaults to `SslProtocols.None` instead of `SslProtocols.Tls12 | SslProtocols.Tls11`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="34eb0-114">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="34eb0-114">Reason for change</span></span>

<span data-ttu-id="34eb0-115">Изменения были внесены для поддержки TLS 1.3 и будущих версий TLS по умолчанию по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="34eb0-115">The change was made to support TLS 1.3 and future TLS versions by default as they become available.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="34eb0-116">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="34eb0-116">Recommended action</span></span>

<span data-ttu-id="34eb0-117">Если к приложению не предъявляется особых требований, следует использовать новые значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34eb0-117">Unless your app has a specific reason not to, you should use the new defaults.</span></span> <span data-ttu-id="34eb0-118">Убедитесь, что ваша система настроена на разрешение только безопасных протоколов.</span><span class="sxs-lookup"><span data-stu-id="34eb0-118">Verify your system is configured to allow only secure protocols.</span></span>

<span data-ttu-id="34eb0-119">Чтобы отключить старые протоколы, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="34eb0-119">To disable older protocols, take one of the following actions:</span></span>

* <span data-ttu-id="34eb0-120">Отключите более старые протоколы, такие как TLS 1.0, на уровне всей системы, руководствуясь [инструкциями для Windows](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry).</span><span class="sxs-lookup"><span data-stu-id="34eb0-120">Disable older protocols, such as TLS 1.0, system-wide with the [Windows instructions](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry).</span></span> <span data-ttu-id="34eb0-121">В настоящее время он включен по умолчанию во всех версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="34eb0-121">It's currently enabled by default on all Windows versions.</span></span>
* <span data-ttu-id="34eb0-122">Вручную выберите протоколы, которые требуется поддерживать в коде, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="34eb0-122">Manually select which protocols you want to support in code as follows:</span></span>

    ```csharp
    using System.Security.Authentication;
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
                    webBuilder.UseKestrel(kestrelOptions =>
                    {
                        kestrelOptions.ConfigureHttpsDefaults(httpsOptions =>
                        {
                            httpsOptions.SslProtocols = SslProtocols.Tls12 | SslProtocols.Tls13;
                        });
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="34eb0-123">К сожалению, нет API для исключения конкретных протоколов.</span><span class="sxs-lookup"><span data-stu-id="34eb0-123">Unfortunately, there's no API to exclude specific protocols.</span></span>

#### <a name="category"></a><span data-ttu-id="34eb0-124">Категория</span><span class="sxs-lookup"><span data-stu-id="34eb0-124">Category</span></span>

<span data-ttu-id="34eb0-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="34eb0-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="34eb0-126">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="34eb0-126">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
