---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621240"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="090e6-101">Рабочий процесс теперь создает исходное исключение вместо NullReferenceException, которое создавалось в некоторых случаях</span><span class="sxs-lookup"><span data-stu-id="090e6-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="090e6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="090e6-102">Details</span></span>

<span data-ttu-id="090e6-103">В .NET Framework 4.6.2 и более ранних версий в тех случаях, когда метод Execute действия рабочего процесса создает исключение со значением <code>null</code> для свойства <xref:System.Exception.Message>, среда выполнения рабочего процесса System.Activities создает исключение <xref:System.NullReferenceException?displayProperty=fullName>, маскируя исходное исключение. В версии .NET Framework 4.7 создается ранее маскированное исключение.</span><span class="sxs-lookup"><span data-stu-id="090e6-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="090e6-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="090e6-104">Suggestion</span></span>

<span data-ttu-id="090e6-105">Если в вашем коде реализуется обработка исключения <xref:System.NullReferenceException?displayProperty=fullName>, измените его для перехвата исключений, которые могут создаваться настраиваемыми действиями.</span><span class="sxs-lookup"><span data-stu-id="090e6-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="090e6-106">name</span><span class="sxs-lookup"><span data-stu-id="090e6-106">Name</span></span>    | <span data-ttu-id="090e6-107">Значение</span><span class="sxs-lookup"><span data-stu-id="090e6-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="090e6-108">Область</span><span class="sxs-lookup"><span data-stu-id="090e6-108">Scope</span></span>   |<span data-ttu-id="090e6-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="090e6-109">Minor</span></span>|
|<span data-ttu-id="090e6-110">Version</span><span class="sxs-lookup"><span data-stu-id="090e6-110">Version</span></span>|<span data-ttu-id="090e6-111">4.7</span><span class="sxs-lookup"><span data-stu-id="090e6-111">4.7</span></span>|
|<span data-ttu-id="090e6-112">Type</span><span class="sxs-lookup"><span data-stu-id="090e6-112">Type</span></span>|<span data-ttu-id="090e6-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="090e6-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="090e6-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="090e6-114">Affected APIs</span></span>

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
