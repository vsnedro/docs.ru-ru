---
ms.openlocfilehash: 61d5885c19e39b138090c1a98fa26348724893c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497494"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="a1e61-101">Рабочий процесс теперь создает исходное исключение вместо NullReferenceException, которое создавалось в некоторых случаях</span><span class="sxs-lookup"><span data-stu-id="a1e61-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="a1e61-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a1e61-102">Details</span></span>

<span data-ttu-id="a1e61-103">В .NET Framework 4.6.2 и более ранних версий в тех случаях, когда метод Execute действия рабочего процесса создает исключение со значением <code>null</code> для свойства <xref:System.Exception.Message>, среда выполнения рабочего процесса System.Activities создает исключение <xref:System.NullReferenceException?displayProperty=fullName>, маскируя исходное исключение. В версии .NET Framework 4.7 создается ранее маскированное исключение.</span><span class="sxs-lookup"><span data-stu-id="a1e61-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a1e61-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="a1e61-104">Suggestion</span></span>

<span data-ttu-id="a1e61-105">Если в вашем коде реализуется обработка исключения <xref:System.NullReferenceException?displayProperty=fullName>, измените его для перехвата исключений, которые могут создаваться настраиваемыми действиями.</span><span class="sxs-lookup"><span data-stu-id="a1e61-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="a1e61-106">Имя</span><span class="sxs-lookup"><span data-stu-id="a1e61-106">Name</span></span>    | <span data-ttu-id="a1e61-107">Значение</span><span class="sxs-lookup"><span data-stu-id="a1e61-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a1e61-108">Область</span><span class="sxs-lookup"><span data-stu-id="a1e61-108">Scope</span></span>   |<span data-ttu-id="a1e61-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="a1e61-109">Minor</span></span>|
|<span data-ttu-id="a1e61-110">Version</span><span class="sxs-lookup"><span data-stu-id="a1e61-110">Version</span></span>|<span data-ttu-id="a1e61-111">4.7</span><span class="sxs-lookup"><span data-stu-id="a1e61-111">4.7</span></span>|
|<span data-ttu-id="a1e61-112">Type</span><span class="sxs-lookup"><span data-stu-id="a1e61-112">Type</span></span>|<span data-ttu-id="a1e61-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="a1e61-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a1e61-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a1e61-114">Affected APIs</span></span>

- <xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)`
- `M:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)`
- ``M:System.Activities.AsyncCodeActivity`1.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)``
- `M:System.Activities.WorkflowInvoker.Invoke`

-->
