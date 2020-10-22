---
ms.openlocfilehash: 8de70b0c445aa48fc4c3249ccfc8c095890fb14c
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050533"
---
### <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="2a6d0-101">Socket.LocalEndPoint обновляется после вызова SendToAsync</span><span class="sxs-lookup"><span data-stu-id="2a6d0-101">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="2a6d0-102"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> теперь обновляет значение свойства <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>, используя локальный адрес сокета.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-102"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2a6d0-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="2a6d0-103">Version introduced</span></span>

<span data-ttu-id="2a6d0-104">5.0 (RC1)</span><span class="sxs-lookup"><span data-stu-id="2a6d0-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="2a6d0-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="2a6d0-105">Change description</span></span>

<span data-ttu-id="2a6d0-106">В предыдущих версиях .NET <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> не изменяет значение свойства <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> для экземпляра сокета.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-106">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="2a6d0-107">Начиная с .NET 5.0 при успешном завершении <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> в качестве значения <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> устанавливается локальный адрес неявно привязанного сокета.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-107">Starting in .NET 5.0, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="2a6d0-108">Это согласуется с поведением <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> и <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-108">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2a6d0-109">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="2a6d0-109">Reason for change</span></span>

<span data-ttu-id="2a6d0-110">Это изменение позволяет [исправить ошибку](https://github.com/dotnet/runtime/issues/915) и обеспечивает согласованность поведения в вариантах `SendTo`.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-110">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2a6d0-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="2a6d0-111">Recommended action</span></span>

<span data-ttu-id="2a6d0-112">Измените любой код, в котором предполагается, что <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> не изменяет значение <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-112">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="2a6d0-113">Категория</span><span class="sxs-lookup"><span data-stu-id="2a6d0-113">Category</span></span>

<span data-ttu-id="2a6d0-114">Сети</span><span class="sxs-lookup"><span data-stu-id="2a6d0-114">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2a6d0-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2a6d0-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

-->
