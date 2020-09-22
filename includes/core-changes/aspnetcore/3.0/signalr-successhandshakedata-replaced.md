---
ms.openlocfilehash: 05aec429e28ef74515ef6988d5b064e6d16b7c1b
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679958"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a>SignalR. Замена HandshakeProtocol.SuccessHandshakeData

Поле [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) было удалено и заменено вспомогательным методом, который создает ответ об успешном подтверждении с учетом определенного `IHubProtocol`.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

`HandshakeProtocol.SuccessHandshakeData` являлось полем `public static ReadOnlyMemory<byte>`.

#### <a name="new-behavior"></a>Новое поведение

`HandshakeProtocol.SuccessHandshakeData` заменено методом `static` `GetSuccessfulHandshake(IHubProtocol protocol)`, который возвращает `ReadOnlyMemory<byte>` на основе указанного протокола.

#### <a name="reason-for-change"></a>Причина изменения

Дополнительные поля были добавлены в _ответ_ подтверждения, которые не являются константами и отличаются в зависимости от выбранного протокола.

#### <a name="recommended-action"></a>Рекомендованное действие

Отсутствует. Этот тип не предназначен для использования из пользовательского кода. Это `public`, поэтому он может быть общим для сервера SignalR и клиента. Он также может использоваться клиентами SignalR пользователя, написанными на .NET. Это изменение не влияет на **пользователей** SignalR.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=nameWithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
