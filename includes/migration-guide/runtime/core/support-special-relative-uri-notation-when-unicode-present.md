---
ms.openlocfilehash: 08a9292c5a41e7b9b7c1bcc18ec96460de19863f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621180"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a><span data-ttu-id="457db-101">Поддержка нотации специального относительного URI при наличии символов Юникода</span><span class="sxs-lookup"><span data-stu-id="457db-101">Support special relative URI notation when Unicode is present</span></span>

#### <a name="details"></a><span data-ttu-id="457db-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="457db-102">Details</span></span>

<span data-ttu-id="457db-103"><xref:System.Uri> больше не будет создавать исключение <xref:System.NullReferenceException> при вызове <xref:System.Uri.TryCreate%2A> для определенных относительных URI, содержащих символы Юникода.</span><span class="sxs-lookup"><span data-stu-id="457db-103"><xref:System.Uri> will no longer throw a <xref:System.NullReferenceException> when calling <xref:System.Uri.TryCreate%2A> on certain relative URIs containing Unicode.</span></span> <span data-ttu-id="457db-104">Простое воспроизведение <xref:System.NullReferenceException> представлено ниже (с двумя эквивалентными инструкциями):</span><span class="sxs-lookup"><span data-stu-id="457db-104">The simplest reproduction of the <xref:System.NullReferenceException> is below, with the two statements being equivalent:</span></span><pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre><span data-ttu-id="457db-105">Для воспроизведения <xref:System.NullReferenceException> должны выполняться следующие условия:</span><span class="sxs-lookup"><span data-stu-id="457db-105">To reproduce the <xref:System.NullReferenceException>, the following items must be true:</span></span><ul><li><span data-ttu-id="457db-106">URI должен быть указан как относительный: с префиксом "http:", за которым не следуют две косые черты "//".</span><span class="sxs-lookup"><span data-stu-id="457db-106">The URI must be specified as relative by prepending it with ‘http:’ and not following it with ‘//’.</span></span></li><li><span data-ttu-id="457db-107">URI должен содержать незарезервированные символы или символы Юникода, закодированные процентами.</span><span class="sxs-lookup"><span data-stu-id="457db-107">The URI must contain percent-encoded Unicode or unreserved symbols.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="457db-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="457db-108">Suggestion</span></span>

<span data-ttu-id="457db-109">Пользователям, зависящим от этого поведения, для запрета относительных URI следует указывать <xref:System.UriKind.Absolute?displayProperty=nameWithType> при создании URI.</span><span class="sxs-lookup"><span data-stu-id="457db-109">Users depending on this behavior to disallow relative URIs should instead specify <xref:System.UriKind.Absolute?displayProperty=nameWithType> when creating a URI.</span></span>

| <span data-ttu-id="457db-110">name</span><span class="sxs-lookup"><span data-stu-id="457db-110">Name</span></span>    | <span data-ttu-id="457db-111">Значение</span><span class="sxs-lookup"><span data-stu-id="457db-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="457db-112">Область</span><span class="sxs-lookup"><span data-stu-id="457db-112">Scope</span></span>   |<span data-ttu-id="457db-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="457db-113">Edge</span></span>|
|<span data-ttu-id="457db-114">Version</span><span class="sxs-lookup"><span data-stu-id="457db-114">Version</span></span>|<span data-ttu-id="457db-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="457db-115">4.7.2</span></span>|
|<span data-ttu-id="457db-116">Type</span><span class="sxs-lookup"><span data-stu-id="457db-116">Type</span></span>|<span data-ttu-id="457db-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="457db-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="457db-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="457db-118">Affected APIs</span></span>

-<xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
