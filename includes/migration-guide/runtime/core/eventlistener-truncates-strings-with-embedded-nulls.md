---
ms.openlocfilehash: 6f5c1ecead4e2f74e621354058aab70bfa1cccb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620565"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="ad651-101">EventListener усекает строки с внедренными значениями NULL</span><span class="sxs-lookup"><span data-stu-id="ad651-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="ad651-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ad651-102">Details</span></span>

<span data-ttu-id="ad651-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> усекает строки с внедренными значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="ad651-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="ad651-104">Символы NULL не поддерживаются классом <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ad651-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="ad651-105">Изменение влияет только на приложения, использующие <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> для чтения данных <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> в процессе и значения NULL в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="ad651-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ad651-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="ad651-106">Suggestion</span></span>

<span data-ttu-id="ad651-107">Если возможно, следует обновить данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>, чтобы не использовать внедренные символы NULL.</span><span class="sxs-lookup"><span data-stu-id="ad651-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="ad651-108">name</span><span class="sxs-lookup"><span data-stu-id="ad651-108">Name</span></span>    | <span data-ttu-id="ad651-109">Значение</span><span class="sxs-lookup"><span data-stu-id="ad651-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ad651-110">Область</span><span class="sxs-lookup"><span data-stu-id="ad651-110">Scope</span></span>   |<span data-ttu-id="ad651-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="ad651-111">Edge</span></span>|
|<span data-ttu-id="ad651-112">Version</span><span class="sxs-lookup"><span data-stu-id="ad651-112">Version</span></span>|<span data-ttu-id="ad651-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="ad651-113">4.5.1</span></span>|
|<span data-ttu-id="ad651-114">Type</span><span class="sxs-lookup"><span data-stu-id="ad651-114">Type</span></span>|<span data-ttu-id="ad651-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ad651-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ad651-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ad651-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Tracing.EventListener.%23ctor></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
