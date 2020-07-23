---
ms.openlocfilehash: 492d3e61acff31d3d6858a1c27cf353b04a05e36
ms.sourcegitcommit: d4f7ba08f2a45a9dbef53be597eed6d4a9410f29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401982"
---
### <a name="security-cookie-name-encoding-removed"></a><span data-ttu-id="b3715-101">Безопасность. Удалена кодировка имен файлов cookie</span><span class="sxs-lookup"><span data-stu-id="b3715-101">Security: Cookie name encoding removed</span></span>

<span data-ttu-id="b3715-102">В соответствии со [стандартом HTTP](https://tools.ietf.org/html/rfc6265#section-4.1.1) в именах и значениях файлов cookie могут использоваться только определенные символы.</span><span class="sxs-lookup"><span data-stu-id="b3715-102">The [HTTP cookie standard](https://tools.ietf.org/html/rfc6265#section-4.1.1) allows only specific characters in cookie names and values.</span></span> <span data-ttu-id="b3715-103">Поддержка недопустимых символов в ASP.NET Core реализуется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b3715-103">To support disallowed characters, ASP.NET Core:</span></span>

* <span data-ttu-id="b3715-104">Кодирование при создании файла cookie ответа.</span><span class="sxs-lookup"><span data-stu-id="b3715-104">Encodes when creating a response cookie.</span></span>
* <span data-ttu-id="b3715-105">Декодирование при чтении файла cookie запроса.</span><span class="sxs-lookup"><span data-stu-id="b3715-105">Decodes when reading a request cookie.</span></span>

<span data-ttu-id="b3715-106">В ASP.NET Core 5.0 это поведение кодирования изменилось в связи выявленными проблемами с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="b3715-106">In ASP.NET Core 5.0, this encoding behavior changed in response to a security concern.</span></span>

<span data-ttu-id="b3715-107">Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span><span class="sxs-lookup"><span data-stu-id="b3715-107">For discussion, see GitHub issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b3715-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b3715-108">Version introduced</span></span>

<span data-ttu-id="b3715-109">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="b3715-109">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b3715-110">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="b3715-110">Old behavior</span></span>

<span data-ttu-id="b3715-111">Имена файлов cookie ответов кодируются.</span><span class="sxs-lookup"><span data-stu-id="b3715-111">Response cookie names are encoded.</span></span> <span data-ttu-id="b3715-112">Имена файлов cookie запросов декодируются.</span><span class="sxs-lookup"><span data-stu-id="b3715-112">Request cookie names are decoded.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b3715-113">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="b3715-113">New behavior</span></span>

<span data-ttu-id="b3715-114">Кодирование и декодирование имен файлов cookie было исключено.</span><span class="sxs-lookup"><span data-stu-id="b3715-114">Encoding and decoding of cookie names was removed.</span></span> <span data-ttu-id="b3715-115">Для предшествующих [поддерживаемых версий](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ASP.NET Core команда разработчиков планирует устранять проблемы с декодированием на местах.</span><span class="sxs-lookup"><span data-stu-id="b3715-115">For prior [supported versions](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) of ASP.NET Core, the team plans to mitigate the decoding issue in-place.</span></span> <span data-ttu-id="b3715-116">Кроме того, при вызове <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> с указанием недопустимого имени файла cookie возникает исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="b3715-116">Additionally, calling <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> with an invalid cookie name throws an exception of type <xref:System.ArgumentException>.</span></span> <span data-ttu-id="b3715-117">Способ кодирования и декодирования значений файлов cookie не изменился.</span><span class="sxs-lookup"><span data-stu-id="b3715-117">Encoding and decoding of cookie values remains unchanged.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b3715-118">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="b3715-118">Reason for change</span></span>

<span data-ttu-id="b3715-119">На [нескольких веб-платформах](https://github.com/advisories/GHSA-j6w9-fv6q-3q52) были обнаружены проблемы.</span><span class="sxs-lookup"><span data-stu-id="b3715-119">An issue was discovered in [multiple web frameworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span></span> <span data-ttu-id="b3715-120">В процессе кодирования и декодирования злоумышленник получал возможность обойти защитную функцию [префиксов файлов cookie](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) путем подмены зарезервированных префиксов, таких как `__Host-`, закодированными значениями, например `__%48ost-`.</span><span class="sxs-lookup"><span data-stu-id="b3715-120">The encoding and decoding could allow an attacker to bypass a security feature called [cookie prefixes](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) by spoofing reserved prefixes like `__Host-` with encoded values like `__%48ost-`.</span></span> <span data-ttu-id="b3715-121">Для проведения такой атаки требуется использовать дополнительную уязвимость веб-сайта для внедрения ложных файлов cookie, например уязвимость межсайтовых сценариев (XSS).</span><span class="sxs-lookup"><span data-stu-id="b3715-121">The attack requires a secondary exploit to inject the spoofed cookies, such as a cross-site scripting (XSS) vulnerability, in the website.</span></span> <span data-ttu-id="b3715-122">По умолчанию эти префиксы не используются в ASP.NET Core, а также в библиотеках или шаблонах `Microsoft.Owin`.</span><span class="sxs-lookup"><span data-stu-id="b3715-122">These prefixes aren't used by default in ASP.NET Core or `Microsoft.Owin` libraries or templates.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b3715-123">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="b3715-123">Recommended action</span></span>

<span data-ttu-id="b3715-124">Если вы переносите проекты в ASP.NET Core 5.0 или более поздней версии, убедитесь, что используемые имена файлов cookie соответствуют [требованиям спецификации токенов](https://tools.ietf.org/html/rfc2616#section-2.2): символы ASCII, за исключением управляющих символов и разделителей `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span><span class="sxs-lookup"><span data-stu-id="b3715-124">If you're moving projects to ASP.NET Core 5.0 or later, ensure that their cookie names conform to the [token specification requirements](https://tools.ietf.org/html/rfc2616#section-2.2): ASCII characters excluding controls and separators `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span></span> <span data-ttu-id="b3715-125">Если в именах файлов cookie или других заголовках HTTP используются не входящие в набор ASCII символы, это может привести к возникновению исключения на сервере или некорректной передаче данных клиенту и обратно.</span><span class="sxs-lookup"><span data-stu-id="b3715-125">The use of non-ASCII characters in cookie names or other HTTP headers may cause an exception from the server or be improperly round-tripped by the client.</span></span>

#### <a name="category"></a><span data-ttu-id="b3715-126">Категория</span><span class="sxs-lookup"><span data-stu-id="b3715-126">Category</span></span>

<span data-ttu-id="b3715-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b3715-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b3715-128">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b3715-128">Affected APIs</span></span>

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
