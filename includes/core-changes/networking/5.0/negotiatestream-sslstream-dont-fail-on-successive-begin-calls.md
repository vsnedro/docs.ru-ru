---
ms.openlocfilehash: 16994e9cd97b31a30c8c5ce49d2042ff79b3f60b
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050532"
---
### <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="3eb21-101">NegotiateStream и SslStream поддерживают последовательные операции Begin</span><span class="sxs-lookup"><span data-stu-id="3eb21-101">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="3eb21-102">Случаи ошибок в потоках безопасности обрабатываются по-разному, а последовательные вызовы `BeginAuthenticateAsServer` или `BeginAuthenticateAsClient` больше не завершаются сбоями.</span><span class="sxs-lookup"><span data-stu-id="3eb21-102">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3eb21-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="3eb21-103">Version introduced</span></span>

<span data-ttu-id="3eb21-104">5.0 (RC1)</span><span class="sxs-lookup"><span data-stu-id="3eb21-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="3eb21-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="3eb21-105">Change description</span></span>

<span data-ttu-id="3eb21-106">В предыдущих версиях .NET последовательный вызов `BeginAuthenticateAsServer` или `BeginAuthenticateAsClient` без предварительного вызова `EndAuthenticateAsServer` или `EndAuthenticateAsClient` приводит к возникновению исключения <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="3eb21-106">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="3eb21-107">Начиная с версии .NET 5.0 последовательные вызовы `BeginAuthenticateAsServer` или `BeginAuthenticateAsClient` больше не приводят к возникновению исключения <xref:System.NotSupportedException>, так как эти API поддерживаются реализацией на основе <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="3eb21-107">Starting in .NET 5.0, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3eb21-108">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="3eb21-108">Reason for change</span></span>

<span data-ttu-id="3eb21-109">Переход внутренней реализации от модели асинхронного программирования (APM) к <xref:System.Threading.Tasks.Task> позволяет повысить производительность и снизить сложность кода.</span><span class="sxs-lookup"><span data-stu-id="3eb21-109">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3eb21-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="3eb21-110">Recommended action</span></span>

<span data-ttu-id="3eb21-111">От разработчика не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="3eb21-111">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="3eb21-112">Категория</span><span class="sxs-lookup"><span data-stu-id="3eb21-112">Category</span></span>

<span data-ttu-id="3eb21-113">Сети</span><span class="sxs-lookup"><span data-stu-id="3eb21-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3eb21-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3eb21-114">Affected APIs</span></span>

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
