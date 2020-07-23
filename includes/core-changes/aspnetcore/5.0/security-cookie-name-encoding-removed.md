---
ms.openlocfilehash: 492d3e61acff31d3d6858a1c27cf353b04a05e36
ms.sourcegitcommit: d4f7ba08f2a45a9dbef53be597eed6d4a9410f29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401982"
---
### <a name="security-cookie-name-encoding-removed"></a>Безопасность. Удалена кодировка имен файлов cookie

В соответствии со [стандартом HTTP](https://tools.ietf.org/html/rfc6265#section-4.1.1) в именах и значениях файлов cookie могут использоваться только определенные символы. Поддержка недопустимых символов в ASP.NET Core реализуется следующим образом:

* Кодирование при создании файла cookie ответа.
* Декодирование при чтении файла cookie запроса.

В ASP.NET Core 5.0 это поведение кодирования изменилось в связи выявленными проблемами с безопасностью.

Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="old-behavior"></a>Старое поведение

Имена файлов cookie ответов кодируются. Имена файлов cookie запросов декодируются.

#### <a name="new-behavior"></a>Новое поведение

Кодирование и декодирование имен файлов cookie было исключено. Для предшествующих [поддерживаемых версий](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ASP.NET Core команда разработчиков планирует устранять проблемы с декодированием на местах. Кроме того, при вызове <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> с указанием недопустимого имени файла cookie возникает исключение <xref:System.ArgumentException>. Способ кодирования и декодирования значений файлов cookie не изменился.

#### <a name="reason-for-change"></a>Причина изменения

На [нескольких веб-платформах](https://github.com/advisories/GHSA-j6w9-fv6q-3q52) были обнаружены проблемы. В процессе кодирования и декодирования злоумышленник получал возможность обойти защитную функцию [префиксов файлов cookie](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) путем подмены зарезервированных префиксов, таких как `__Host-`, закодированными значениями, например `__%48ost-`. Для проведения такой атаки требуется использовать дополнительную уязвимость веб-сайта для внедрения ложных файлов cookie, например уязвимость межсайтовых сценариев (XSS). По умолчанию эти префиксы не используются в ASP.NET Core, а также в библиотеках или шаблонах `Microsoft.Owin`.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы переносите проекты в ASP.NET Core 5.0 или более поздней версии, убедитесь, что используемые имена файлов cookie соответствуют [требованиям спецификации токенов](https://tools.ietf.org/html/rfc2616#section-2.2): символы ASCII, за исключением управляющих символов и разделителей `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`. Если в именах файлов cookie или других заголовках HTTP используются не входящие в набор ASCII символы, это может привести к возникновению исключения на сервере или некорректной передаче данных клиенту и обратно.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
