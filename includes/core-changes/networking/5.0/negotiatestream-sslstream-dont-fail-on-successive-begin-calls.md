---
ms.openlocfilehash: 16994e9cd97b31a30c8c5ce49d2042ff79b3f60b
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050532"
---
### <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a>NegotiateStream и SslStream поддерживают последовательные операции Begin

Случаи ошибок в потоках безопасности обрабатываются по-разному, а последовательные вызовы `BeginAuthenticateAsServer` или `BeginAuthenticateAsClient` больше не завершаются сбоями.

#### <a name="version-introduced"></a>Представленная версия

5.0 (RC1)

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET последовательный вызов `BeginAuthenticateAsServer` или `BeginAuthenticateAsClient` без предварительного вызова `EndAuthenticateAsServer` или `EndAuthenticateAsClient` приводит к возникновению исключения <xref:System.NotSupportedException>. Начиная с версии .NET 5.0 последовательные вызовы `BeginAuthenticateAsServer` или `BeginAuthenticateAsClient` больше не приводят к возникновению исключения <xref:System.NotSupportedException>, так как эти API поддерживаются реализацией на основе <xref:System.Threading.Tasks.Task>.

#### <a name="reason-for-change"></a>Причина изменения

Переход внутренней реализации от модели асинхронного программирования (APM) к <xref:System.Threading.Tasks.Task> позволяет повысить производительность и снизить сложность кода.

#### <a name="recommended-action"></a>Рекомендованное действие

От разработчика не требуется никаких действий.

#### <a name="category"></a>Категория

Сети

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

-->
