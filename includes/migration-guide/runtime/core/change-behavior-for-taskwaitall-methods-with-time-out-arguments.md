---
ms.openlocfilehash: 9d0791f00db7d830fc5d327af30218a0bbfcb25f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496655"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a><span data-ttu-id="64eee-101">Изменение в поведении методов Task.WaitAll с аргументами времени ожидания</span><span class="sxs-lookup"><span data-stu-id="64eee-101">Change in behavior for Task.WaitAll methods with time-out arguments</span></span>

#### <a name="details"></a><span data-ttu-id="64eee-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="64eee-102">Details</span></span>

<span data-ttu-id="64eee-103">В .NET Framework 4.5 реализовано согласованное поведение методов <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>. В .NET Framework 4 поведение этих методов было непоследовательным.</span><span class="sxs-lookup"><span data-stu-id="64eee-103"><xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> behavior was made more consistent in .NET Framework 4.5.In the .NET Framework 4, these methods behaved inconsistently.</span></span> <span data-ttu-id="64eee-104">По истечении времени ожидания, если одна или несколько задач были завершены или отменены до вызова метода, метод вызывал исключение <xref:System.AggregateException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="64eee-104">When the time-out expired, if one or more tasks were completed or canceled before the method call, the method threw an <xref:System.AggregateException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="64eee-105">По истечении времени ожидания, если ни одна задача не была завершена или отменена до вызова метода, однако одна или несколько задач входили в эти состояния после вызова метода, метод возвращал значение false.</span><span class="sxs-lookup"><span data-stu-id="64eee-105">When the time-out expired, if no tasks were completed or canceled before the method call, but one or more tasks entered these states after the method call, the method returned false.</span></span><br/><br/><span data-ttu-id="64eee-106">В .NET Framework 4.5 эти перегрузки метода теперь возвращают false, если все задачи по-прежнему выполняются после истечения времени ожидания, и вызывают исключение <xref:System.AggregateException?displayProperty=fullName>, только если входная задача была отменена (независимо от того, была ли она до или после вызова метода), а никакие другие задачи не выполняются.</span><span class="sxs-lookup"><span data-stu-id="64eee-106">In the .NET Framework 4.5, these method overloads now return false if any tasks are still running when the time-out interval expired, and they throw an <xref:System.AggregateException?displayProperty=fullName> exception only if an input task was cancelled (regardless of whether it was before or after the method call) and no other tasks are still running.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="64eee-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="64eee-107">Suggestion</span></span>

<span data-ttu-id="64eee-108">Если исключение <xref:System.AggregateException?displayProperty=fullName> было перехвачено с целью обнаружения задачи, которая была отменена до вызова метода <xref:System.Threading.Tasks.Task.WaitAll%2A>, этот код должен выполнить то же обнаружение с помощью свойства <xref:System.Threading.Tasks.Task.IsCanceled%2A> (например, .Any(t =&gt; t.IsCanceled)), так как .NET Framework 4.6 создаст исключение только в том случае, если все ожидаемые задачи завершены до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="64eee-108">If an <xref:System.AggregateException?displayProperty=fullName> was being caught as a means of detecting a task that was cancelled prior to the <xref:System.Threading.Tasks.Task.WaitAll%2A> call being invoked, that code should instead do the same detection via the  <xref:System.Threading.Tasks.Task.IsCanceled%2A> property (for example: .Any(t =&gt; t.IsCanceled)) since .NET Framework 4.6 will only throw in that case if all awaited tasks are completed prior to the timeout.</span></span>

| <span data-ttu-id="64eee-109">name</span><span class="sxs-lookup"><span data-stu-id="64eee-109">Name</span></span>    | <span data-ttu-id="64eee-110">Значение</span><span class="sxs-lookup"><span data-stu-id="64eee-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="64eee-111">Область</span><span class="sxs-lookup"><span data-stu-id="64eee-111">Scope</span></span>   |<span data-ttu-id="64eee-112">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="64eee-112">Minor</span></span>|
|<span data-ttu-id="64eee-113">Version</span><span class="sxs-lookup"><span data-stu-id="64eee-113">Version</span></span>|<span data-ttu-id="64eee-114">4.5</span><span class="sxs-lookup"><span data-stu-id="64eee-114">4.5</span></span>|
|<span data-ttu-id="64eee-115">Type</span><span class="sxs-lookup"><span data-stu-id="64eee-115">Type</span></span>|<span data-ttu-id="64eee-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="64eee-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64eee-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="64eee-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)`

-->
