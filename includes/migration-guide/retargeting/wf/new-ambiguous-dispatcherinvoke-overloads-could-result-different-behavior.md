---
ms.openlocfilehash: 80e61d4dd5b8d4754a39e95e37475fefff57fcbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617264"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a><span data-ttu-id="bfc13-101">Новые (неоднозначные) перегрузки Dispatcher.Invoke могут привести к изменению поведения</span><span class="sxs-lookup"><span data-stu-id="bfc13-101">New (ambiguous) Dispatcher.Invoke overloads could result in different behavior</span></span>

#### <a name="details"></a><span data-ttu-id="bfc13-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="bfc13-102">Details</span></span>

<span data-ttu-id="bfc13-103">В .NET Framework 4.5 добавлены новые перегрузки в метод <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType>, включающие параметр типа <xref:System.Action>.</span><span class="sxs-lookup"><span data-stu-id="bfc13-103">The .NET Framework 4.5 adds new overloads to <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> that include a parameter of type <xref:System.Action>.</span></span> <span data-ttu-id="bfc13-104">Если существующий код перекомпилируется, компиляторы могут разрешить вызовы методов Dispatcher.Invoke, имеющие параметр <xref:System.Delegate>, как вызовы методов Dispatcher.Invoke с параметром <xref:System.Action>.</span><span class="sxs-lookup"><span data-stu-id="bfc13-104">When existing code is recompiled, compilers may resolve calls to Dispatcher.Invoke methods that have a <xref:System.Delegate> parameter as calls to Dispatcher.Invoke methods with an <xref:System.Action> parameter.</span></span> <span data-ttu-id="bfc13-105">Если вызов перегрузки Dispatcher.Invoke с параметром <xref:System.Delegate> разрешается как вызов перегрузки Dispatcher.Invoke с параметром <xref:System.Action>, возможны следующие различия в поведении.</span><span class="sxs-lookup"><span data-stu-id="bfc13-105">If a call to a Dispatcher.Invoke overload with a  <xref:System.Delegate> parameter is resolved as a call to a Dispatcher.Invoke overload with an <xref:System.Action> parameter, the following differences in behavior may occur:</span></span>

- <span data-ttu-id="bfc13-106">При возникновении исключения события <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> и <xref:System.Windows.Threading.Dispatcher.UnhandledException> не вызываются.</span><span class="sxs-lookup"><span data-stu-id="bfc13-106">If an exception occurs, the <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> and <xref:System.Windows.Threading.Dispatcher.UnhandledException> events are not raised.</span></span> <span data-ttu-id="bfc13-107">Вместо этого исключения обрабатываются событием <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="bfc13-107">Instead, exceptions are handled by the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName> event.</span></span>
- <span data-ttu-id="bfc13-108">Вызовы некоторых членов, например свойства <xref:System.Windows.Threading.DispatcherOperation.Result>, блокируются до тех пор, пока операция не будет завершена.</span><span class="sxs-lookup"><span data-stu-id="bfc13-108">Calls to some members, such as <xref:System.Windows.Threading.DispatcherOperation.Result>, block until the operation has completed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bfc13-109">Предложение</span><span class="sxs-lookup"><span data-stu-id="bfc13-109">Suggestion</span></span>

<span data-ttu-id="bfc13-110">Чтобы избежать неоднозначности (и потенциальных различий в обработке исключений и поведениях блокировки), код, вызывающий Dispatcher.Invoke, может передать пустой object[] как второй параметр в вызов Invoke, чтобы гарантировать разрешение перегрузки метода в .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="bfc13-110">To avoid ambiguity (and potential differences in exception handling or blocking behaviors), code calling Dispatcher.Invoke can pass an empty object[] as a second parameter to the Invoke call to be sure of resolving to the .NET Framework 4.0 method overload.</span></span>

| <span data-ttu-id="bfc13-111">name</span><span class="sxs-lookup"><span data-stu-id="bfc13-111">Name</span></span>    | <span data-ttu-id="bfc13-112">Значение</span><span class="sxs-lookup"><span data-stu-id="bfc13-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bfc13-113">Область</span><span class="sxs-lookup"><span data-stu-id="bfc13-113">Scope</span></span>   | <span data-ttu-id="bfc13-114">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="bfc13-114">Minor</span></span>       |
| <span data-ttu-id="bfc13-115">Version</span><span class="sxs-lookup"><span data-stu-id="bfc13-115">Version</span></span> | <span data-ttu-id="bfc13-116">4.5</span><span class="sxs-lookup"><span data-stu-id="bfc13-116">4.5</span></span>         |
| <span data-ttu-id="bfc13-117">Type</span><span class="sxs-lookup"><span data-stu-id="bfc13-117">Type</span></span>    | <span data-ttu-id="bfc13-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="bfc13-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="bfc13-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="bfc13-119">Affected APIs</span></span>

- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
