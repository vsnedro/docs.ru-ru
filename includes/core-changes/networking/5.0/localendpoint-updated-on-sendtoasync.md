---
ms.openlocfilehash: 8de70b0c445aa48fc4c3249ccfc8c095890fb14c
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050533"
---
### <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a>Socket.LocalEndPoint обновляется после вызова SendToAsync

<xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> теперь обновляет значение свойства <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>, используя локальный адрес сокета.

#### <a name="version-introduced"></a>Представленная версия

5.0 (RC1)

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> не изменяет значение свойства <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> для экземпляра сокета. Начиная с .NET 5.0 при успешном завершении <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> в качестве значения <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> устанавливается локальный адрес неявно привязанного сокета. Это согласуется с поведением <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> и <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение позволяет [исправить ошибку](https://github.com/dotnet/runtime/issues/915) и обеспечивает согласованность поведения в вариантах `SendTo`.

#### <a name="recommended-action"></a>Рекомендованное действие

Измените любой код, в котором предполагается, что <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> не изменяет значение <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

Сети

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

-->
