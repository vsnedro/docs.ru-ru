---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496142"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="2fd5f-101">EventListener усекает строки с внедренными значениями NULL</span><span class="sxs-lookup"><span data-stu-id="2fd5f-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="2fd5f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2fd5f-102">Details</span></span>

<span data-ttu-id="2fd5f-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> усекает строки с внедренными значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="2fd5f-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="2fd5f-104">Символы NULL не поддерживаются классом <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2fd5f-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="2fd5f-105">Изменение влияет только на приложения, использующие <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> для чтения данных <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> в процессе и значения NULL в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="2fd5f-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2fd5f-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="2fd5f-106">Suggestion</span></span>

<span data-ttu-id="2fd5f-107">Если возможно, следует обновить данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>, чтобы не использовать внедренные символы NULL.</span><span class="sxs-lookup"><span data-stu-id="2fd5f-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="2fd5f-108">name</span><span class="sxs-lookup"><span data-stu-id="2fd5f-108">Name</span></span>    | <span data-ttu-id="2fd5f-109">Значение</span><span class="sxs-lookup"><span data-stu-id="2fd5f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2fd5f-110">Область</span><span class="sxs-lookup"><span data-stu-id="2fd5f-110">Scope</span></span>   |<span data-ttu-id="2fd5f-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="2fd5f-111">Edge</span></span>|
|<span data-ttu-id="2fd5f-112">Version</span><span class="sxs-lookup"><span data-stu-id="2fd5f-112">Version</span></span>|<span data-ttu-id="2fd5f-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="2fd5f-113">4.5.1</span></span>|
|<span data-ttu-id="2fd5f-114">Type</span><span class="sxs-lookup"><span data-stu-id="2fd5f-114">Type</span></span>|<span data-ttu-id="2fd5f-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2fd5f-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2fd5f-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2fd5f-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
