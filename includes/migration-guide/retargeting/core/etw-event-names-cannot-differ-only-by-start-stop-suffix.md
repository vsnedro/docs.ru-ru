---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614676"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="8b7d5-101">Имена событий в трассировке событий Windows не должны отличаться друг от друга только суффиксами "Start" или "Stop"</span><span class="sxs-lookup"><span data-stu-id="8b7d5-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

#### <a name="details"></a><span data-ttu-id="8b7d5-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="8b7d5-102">Details</span></span>

<span data-ttu-id="8b7d5-103">В .NET Framework 4.6 и 4.6.1 среда выполнения вызывает исключение <xref:System.ArgumentException>, когда имена двух событий в трассировке событий Windows отличаются только суффиксами Start или Stop (например, когда имя одного события `LogUser`, а другого — `LogUserStart`).</span><span class="sxs-lookup"><span data-stu-id="8b7d5-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a "Start" or "Stop" suffix (as when one event is named `LogUser` and another is named `LogUserStart`).</span></span> <span data-ttu-id="8b7d5-104">В этом случае среда выполнения не может определить источник событий и, соответственно, сделать запись в журнале.</span><span class="sxs-lookup"><span data-stu-id="8b7d5-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8b7d5-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="8b7d5-105">Suggestion</span></span>

<span data-ttu-id="8b7d5-106">Чтобы предотвратить возникновение исключения, убедитесь, что имена событий отличаются не только суффиксами Start или Stop. Это требование снято в .NET Framework 4.6.2 и более поздних версий. Среда выполнения может устранить неоднозначность имен событий, которые отличаются только суффиксами Start и Stop.</span><span class="sxs-lookup"><span data-stu-id="8b7d5-106">To prevent the exception, ensure that no two event names differ only by a "Start" or "Stop" suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the "Start" and "Stop" suffix.</span></span>

| <span data-ttu-id="8b7d5-107">name</span><span class="sxs-lookup"><span data-stu-id="8b7d5-107">Name</span></span>    | <span data-ttu-id="8b7d5-108">Значение</span><span class="sxs-lookup"><span data-stu-id="8b7d5-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8b7d5-109">Область</span><span class="sxs-lookup"><span data-stu-id="8b7d5-109">Scope</span></span>   | <span data-ttu-id="8b7d5-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="8b7d5-110">Edge</span></span>        |
| <span data-ttu-id="8b7d5-111">Version</span><span class="sxs-lookup"><span data-stu-id="8b7d5-111">Version</span></span> | <span data-ttu-id="8b7d5-112">4.6</span><span class="sxs-lookup"><span data-stu-id="8b7d5-112">4.6</span></span>         |
| <span data-ttu-id="8b7d5-113">Type</span><span class="sxs-lookup"><span data-stu-id="8b7d5-113">Type</span></span>    | <span data-ttu-id="8b7d5-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="8b7d5-114">Retargeting</span></span> |
