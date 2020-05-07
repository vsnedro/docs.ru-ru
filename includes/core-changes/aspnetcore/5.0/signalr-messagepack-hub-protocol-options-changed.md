---
ms.openlocfilehash: 7a05f60cf1c04d3d73dadb54541254a83b4ea855
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507100"
---
### <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="50702-101">SignalR. Тип параметров протокола концентратора MessagePack изменился</span><span class="sxs-lookup"><span data-stu-id="50702-101">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="50702-102">Тип параметров протокола концентратора MessagePack ASP.NET Core SignalR изменился с `IList<MessagePack.IFormatterResolver>` на тип `MessagePackSerializerOptions` библиотеки [MessagePack](https://www.nuget.org/packages/MessagePack).</span><span class="sxs-lookup"><span data-stu-id="50702-102">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="50702-103">Обсуждение этого изменения см. на странице [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span><span class="sxs-lookup"><span data-stu-id="50702-103">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="50702-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="50702-104">Version introduced</span></span>

<span data-ttu-id="50702-105">5.0, предварительная версия 4</span><span class="sxs-lookup"><span data-stu-id="50702-105">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="50702-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="50702-106">Old behavior</span></span>

<span data-ttu-id="50702-107">Можно добавить параметры, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="50702-107">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="50702-108">И заменить параметры следующим образом:</span><span class="sxs-lookup"><span data-stu-id="50702-108">And replace the options as follows:</span></span>

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

#### <a name="new-behavior"></a><span data-ttu-id="50702-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="50702-109">New behavior</span></span>

<span data-ttu-id="50702-110">Можно добавить параметры, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="50702-110">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="50702-111">И заменить параметры следующим образом:</span><span class="sxs-lookup"><span data-stu-id="50702-111">And replace the options as follows:</span></span>

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

#### <a name="reason-for-change"></a><span data-ttu-id="50702-112">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="50702-112">Reason for change</span></span>

<span data-ttu-id="50702-113">Это изменение является частью перехода к MessagePack v2.x, который был объявлен на странице [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span><span class="sxs-lookup"><span data-stu-id="50702-113">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="50702-114">В библиотеку v2.x добавлен API параметров, который проще в использовании и предоставляет больше возможностей, чем список `MessagePack.IFormatterResolver`, представленный ранее.</span><span class="sxs-lookup"><span data-stu-id="50702-114">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="50702-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="50702-115">Recommended action</span></span>

<span data-ttu-id="50702-116">Это критическое изменение затрагивает всех, кто настраивает значения на <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span><span class="sxs-lookup"><span data-stu-id="50702-116">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="50702-117">Если вы используете протокол концентратора MessagePack ASP.NET Core SignalR и изменяете параметры, внесите изменения, чтобы использовать новый API параметров, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="50702-117">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

#### <a name="category"></a><span data-ttu-id="50702-118">Категория</span><span class="sxs-lookup"><span data-stu-id="50702-118">Category</span></span>

<span data-ttu-id="50702-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="50702-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="50702-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="50702-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
