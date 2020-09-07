---
ms.openlocfilehash: 277a91fbfbf0c6aaaa0dc044ef0c079ad8607699
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496379"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="95885-101">BlockingCollection&lt;T&gt;.TryTakeFromAny больше не вызывает исключение</span><span class="sxs-lookup"><span data-stu-id="95885-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

#### <a name="details"></a><span data-ttu-id="95885-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="95885-102">Details</span></span>

<span data-ttu-id="95885-103">Метод <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> больше не возвращает -1 и <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> больше не вызывает исключение, если одна из коллекций помечена как завершенная.</span><span class="sxs-lookup"><span data-stu-id="95885-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="95885-104">Это изменение позволяет работать с коллекциями, если одна из коллекций пуста или завершена, но другая коллекция по-прежнему содержит элементы, которые можно извлечь.</span><span class="sxs-lookup"><span data-stu-id="95885-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="95885-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="95885-105">Suggestion</span></span>

<span data-ttu-id="95885-106">Если метод TryTakeFromAny, возвращающий -1, и метод TakeFromAny, создающий исключение, использовались в целях управления потоком при заполнении заблокированной коллекции, такой код следует изменить для использования <code>.Any(b =&gt; b.IsCompleted)</code> для обнаружения этого условия.</span><span class="sxs-lookup"><span data-stu-id="95885-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>

| <span data-ttu-id="95885-107">name</span><span class="sxs-lookup"><span data-stu-id="95885-107">Name</span></span>    | <span data-ttu-id="95885-108">Значение</span><span class="sxs-lookup"><span data-stu-id="95885-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="95885-109">Область</span><span class="sxs-lookup"><span data-stu-id="95885-109">Scope</span></span>   |<span data-ttu-id="95885-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="95885-110">Minor</span></span>|
|<span data-ttu-id="95885-111">Version</span><span class="sxs-lookup"><span data-stu-id="95885-111">Version</span></span>|<span data-ttu-id="95885-112">4.5</span><span class="sxs-lookup"><span data-stu-id="95885-112">4.5</span></span>|
|<span data-ttu-id="95885-113">Type</span><span class="sxs-lookup"><span data-stu-id="95885-113">Type</span></span>|<span data-ttu-id="95885-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="95885-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="95885-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="95885-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Threading.CancellationToken)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Int32)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``

-->
