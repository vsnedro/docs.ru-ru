---
ms.openlocfilehash: 7a05f60cf1c04d3d73dadb54541254a83b4ea855
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507100"
---
### <a name="signalr-messagepack-hub-protocol-options-type-changed"></a>SignalR. Тип параметров протокола концентратора MessagePack изменился

Тип параметров протокола концентратора MessagePack ASP.NET Core SignalR изменился с `IList<MessagePack.IFormatterResolver>` на тип `MessagePackSerializerOptions` библиотеки [MessagePack](https://www.nuget.org/packages/MessagePack).

Обсуждение этого изменения см. на странице [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 4

#### <a name="old-behavior"></a>Старое поведение

Можно добавить параметры, как показано в следующем примере:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

И заменить параметры следующим образом:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers = new List<MessagePack.IFormatterResolver>()
        {
            MessagePack.Resolvers.StandardResolver.Instance
        };
    });
```

#### <a name="new-behavior"></a>Новое поведение

Можно добавить параметры, как показано в следующем примере:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

И заменить параметры следующим образом:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions = MessagePackSerializerOptions
                .Standard
                .WithResolver(MessagePack.Resolvers.StandardResolver.Instance)
                .WithSecurity(MessagePackSecurity.UntrustedData);
    });
```

#### <a name="reason-for-change"></a>Причина изменения

Это изменение является частью перехода к MessagePack v2.x, который был объявлен на странице [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404). В библиотеку v2.x добавлен API параметров, который проще в использовании и предоставляет больше возможностей, чем список `MessagePack.IFormatterResolver`, представленный ранее.

#### <a name="recommended-action"></a>Рекомендованное действие

Это критическое изменение затрагивает всех, кто настраивает значения на <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>. Если вы используете протокол концентратора MessagePack ASP.NET Core SignalR и изменяете параметры, внесите изменения, чтобы использовать новый API параметров, как показано выше.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
