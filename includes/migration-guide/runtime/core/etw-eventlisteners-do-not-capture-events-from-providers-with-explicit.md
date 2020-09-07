---
ms.openlocfilehash: 5a96b40e5e0df6a47415acecab410444a713632b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496205"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a><span data-ttu-id="5f261-101">EventListeners трассировки событий Windows не выполняют запись событий от поставщиков с явными ключевыми словами (например, от поставщика TPL)</span><span class="sxs-lookup"><span data-stu-id="5f261-101">ETW EventListeners do not capture events from providers with explicit keywords (like the TPL provider)</span></span>

#### <a name="details"></a><span data-ttu-id="5f261-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5f261-102">Details</span></span>

<span data-ttu-id="5f261-103">EventListeners трассировки событий Windows с пустой маской ключевого слова неправильно записывают события от поставщиков с явными ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="5f261-103">ETW EventListeners with a blank keyword mask do not properly capture events from providers with explicit keywords.</span></span> <span data-ttu-id="5f261-104">В платформе .NET Framework 4.5 поставщик TPL начал предоставлять явные ключевые слова и привел к возникновению этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="5f261-104">In the .NET Framework 4.5, the TPL provider began providing explicit keywords and triggered this issue.</span></span> <span data-ttu-id="5f261-105">В .NET Framework 4.6 EventListeners были обновлены, чтобы больше не вызывать эту проблему.</span><span class="sxs-lookup"><span data-stu-id="5f261-105">In the .NET Framework 4.6, EventListeners have been updated to no longer have this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5f261-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="5f261-106">Suggestion</span></span>

<span data-ttu-id="5f261-107">Чтобы обойти эту проблему, замените вызовы <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> вызовами к перегрузке EnableEvents, которая явно задает маску &quot;любые ключевые слова&quot;: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5f261-107">To work around this problem, replace calls to <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> with calls to the EnableEvents overload that explicitly specifies the &quot;any keywords&quot; mask to use: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>.Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="5f261-108">name</span><span class="sxs-lookup"><span data-stu-id="5f261-108">Name</span></span>    | <span data-ttu-id="5f261-109">Значение</span><span class="sxs-lookup"><span data-stu-id="5f261-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5f261-110">Область</span><span class="sxs-lookup"><span data-stu-id="5f261-110">Scope</span></span>   |<span data-ttu-id="5f261-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="5f261-111">Edge</span></span>|
|<span data-ttu-id="5f261-112">Version</span><span class="sxs-lookup"><span data-stu-id="5f261-112">Version</span></span>|<span data-ttu-id="5f261-113">4.5</span><span class="sxs-lookup"><span data-stu-id="5f261-113">4.5</span></span>|
|<span data-ttu-id="5f261-114">Type</span><span class="sxs-lookup"><span data-stu-id="5f261-114">Type</span></span>|<span data-ttu-id="5f261-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="5f261-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5f261-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5f261-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`

-->
