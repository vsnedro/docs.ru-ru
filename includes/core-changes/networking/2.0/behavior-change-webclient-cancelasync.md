---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859637"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a>WebClient.CancelAsync не всегда сразу отменяет запрос

Начиная с .NET Core 2.0 вызов <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> не отменяет запрос сразу, если ответ начал поступать.

#### <a name="change-description"></a>Описание изменений

Ранее вызов <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> отменял запрос сразу. Начиная с .NET Core 2.0 вызов <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> отменяет запрос сразу, только если ответ не начал поступать. Если ответ начал поступать, запрос отменяется только после считывания полного ответа.

Это изменение было реализовано, так как API <xref:System.Net.WebClient> является нерекомендуемым и заменен на <xref:System.Net.Http.HttpClient>.

#### <a name="version-introduced"></a>Представленная версия

2.0

#### <a name="recommended-action"></a>Рекомендованное действие

Используйте класс <xref:System.Net.Http.HttpClient?displayProperty=fullName> вместо <xref:System.Net.WebClient?displayProperty=fullName>, который является нерекомендуемым.

#### <a name="category"></a>Категория

Сети

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
