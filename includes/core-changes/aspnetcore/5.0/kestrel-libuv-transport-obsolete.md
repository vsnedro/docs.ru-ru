---
ms.openlocfilehash: 203d75f5858c8ff039cf579c0539efda0c5c9f02
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474386"
---
### <a name="kestrel-libuv-transport-marked-as-obsolete"></a>Kestrel. Транспорт Libuv помечен как устаревший

В более ранних версиях ASP.NET Core в качестве сведений о реализации асинхронного ввода и вывода использовались Libuv. В ASP.NET Core 2.0 был разработан альтернативный транспорт на основе <xref:System.Net.Sockets.Socket>. В ASP.NET Core 2.1 Kestrel переключается на использование транспорта на основе `Socket` по умолчанию. Поддержка Libuv сохранялась по соображениям совместимости.

На этом этапе использование транспорта на основе `Socket`гораздо более распространено, чем транспорт Libuv. Следовательно, поддержка Libuv помечена как устаревшая в .NET 5.0 и будет полностью удалена в .NET 6.0.

В рамках этого изменения поддержка Libuv для новых платформ операционной системы (например, Windows ARM64) не будет добавлена в .NET 5.0.

Сведения о критических проблемах, требующих использования транспорта Libuv, см. в GitHub в разделе [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="old-behavior"></a>Старое поведение

API-интерфейсы Libuv не помечены как устаревшие.

#### <a name="new-behavior"></a>Новое поведение

API-интерфейсы Libuv помечены как устаревшие.

#### <a name="reason-for-change"></a>Причина изменения

По умолчанию используется транспорт на основе `Socket`. Нет никаких причин для продолжения использования транспорта Libuv.

#### <a name="recommended-action"></a>Рекомендованное действие

Прекращение использования [пакета Libuv](https://www.nuget.org/packages/Libuv) и методов расширения.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- [WebHostBuilderLibuvExtensions](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [WebHostBuilderLibuvExtensions.UseLibuv](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
