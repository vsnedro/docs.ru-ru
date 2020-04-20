---
ms.openlocfilehash: 6be98e7ced6608ba0793c635adfe61c8b1a7e9d9
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274708"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a><span data-ttu-id="4acfc-101">SignalR. Изменение конструкторов HubConnectionContext</span><span class="sxs-lookup"><span data-stu-id="4acfc-101">SignalR: HubConnectionContext constructors changed</span></span>

<span data-ttu-id="4acfc-102">Конструкторы `HubConnectionContext` SignalR были изменены, чтобы принимать тип параметров, а не несколько параметров, для добавления параметров в будущем.</span><span class="sxs-lookup"><span data-stu-id="4acfc-102">SignalR's `HubConnectionContext` constructors changed to accept an options type, rather than multiple parameters, to future-proof adding options.</span></span> <span data-ttu-id="4acfc-103">Это изменение заменяет два конструктора одним конструктором, принимающим тип параметров.</span><span class="sxs-lookup"><span data-stu-id="4acfc-103">This change replaces two constructors with a single constructor that accepts an options type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4acfc-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="4acfc-104">Version introduced</span></span>

<span data-ttu-id="4acfc-105">3.0</span><span class="sxs-lookup"><span data-stu-id="4acfc-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4acfc-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="4acfc-106">Old behavior</span></span>

<span data-ttu-id="4acfc-107">`HubConnectionContext` имеет два конструктора:</span><span class="sxs-lookup"><span data-stu-id="4acfc-107">`HubConnectionContext` has two constructors:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a><span data-ttu-id="4acfc-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="4acfc-108">New behavior</span></span>

<span data-ttu-id="4acfc-109">Два конструктора были удалены и заменены одним конструктором:</span><span class="sxs-lookup"><span data-stu-id="4acfc-109">The two constructors were removed and replaced with one constructor:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a><span data-ttu-id="4acfc-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="4acfc-110">Reason for change</span></span>

<span data-ttu-id="4acfc-111">Новый конструктор использует новый объект параметров.</span><span class="sxs-lookup"><span data-stu-id="4acfc-111">The new constructor uses a new options object.</span></span> <span data-ttu-id="4acfc-112">Следовательно, функции `HubConnectionContext` можно расширить в будущем, не создавая дополнительные конструкторы и не внося критические изменения.</span><span class="sxs-lookup"><span data-stu-id="4acfc-112">Consequently, the features of `HubConnectionContext` can be expanded in the future without making more constructors and breaking changes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4acfc-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="4acfc-113">Recommended action</span></span>

<span data-ttu-id="4acfc-114">Вместо использования следующего конструктора:</span><span class="sxs-lookup"><span data-stu-id="4acfc-114">Instead of using the following constructor:</span></span>

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

<span data-ttu-id="4acfc-115">Используйте следующий конструктор:</span><span class="sxs-lookup"><span data-stu-id="4acfc-115">Use the following constructor:</span></span>

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a><span data-ttu-id="4acfc-116">Категория</span><span class="sxs-lookup"><span data-stu-id="4acfc-116">Category</span></span>

<span data-ttu-id="4acfc-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4acfc-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4acfc-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4acfc-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
