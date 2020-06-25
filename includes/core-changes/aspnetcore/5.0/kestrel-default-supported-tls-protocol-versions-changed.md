---
ms.openlocfilehash: 3244a36808fb687663241e704d08775ea5c96720
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803240"
---
### <a name="kestrel-default-supported-tls-protocol-versions-changed"></a>Kestrel. Изменены поддерживаемые версии протокола TLS по умолчанию

В Kestrel теперь используются стандартные версии протокола TLS, а не ограничивается лишь протоколами TLS 1.1 и TLS 1.2, как это было ранее.

Это изменение позволяет:

* использовать протокол TLS 1.3 по умолчанию в средах, поддерживающих его;
* использовать TLS 1.0 в некоторых средах (например, в Windows Server 2016 по умолчанию), в которых делать это обычно [нежелательно](/security/engineering/solving-tls1-problem).

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 6

#### <a name="old-behavior"></a>Старое поведение

Kestrel требовалось, чтобы для подключений по умолчанию использовался TLS 1.1 или TLS 1.2.

#### <a name="new-behavior"></a>Новое поведение

Kestrel позволяет операционной системе выбрать наилучший протокол для использования и блокирования небезопасных протоколов. <xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> теперь по умолчанию использует `SslProtocols.None` вместо `SslProtocols.Tls12 | SslProtocols.Tls11`.

#### <a name="reason-for-change"></a>Причина изменения

Изменения были внесены для поддержки TLS 1.3 и будущих версий TLS по умолчанию по мере их появления.

#### <a name="recommended-action"></a>Рекомендованное действие

Если к приложению не предъявляется особых требований, следует использовать новые значения по умолчанию. Убедитесь, что ваша система настроена на разрешение только безопасных протоколов.

Чтобы отключить старые протоколы, выполните одно из следующих действий.

* Отключите более старые протоколы, такие как TLS 1.0, на уровне всей системы, руководствуясь [инструкциями для Windows](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry). В настоящее время он включен по умолчанию во всех версиях Windows.
* Вручную выберите протоколы, которые требуется поддерживать в коде, следующим образом:

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

К сожалению, нет API для исключения конкретных протоколов.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
