---
ms.openlocfilehash: 61d5885c19e39b138090c1a98fa26348724893c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497494"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>Рабочий процесс теперь создает исходное исключение вместо NullReferenceException, которое создавалось в некоторых случаях

#### <a name="details"></a>Подробнее

В .NET Framework 4.6.2 и более ранних версий в тех случаях, когда метод Execute действия рабочего процесса создает исключение со значением <code>null</code> для свойства <xref:System.Exception.Message>, среда выполнения рабочего процесса System.Activities создает исключение <xref:System.NullReferenceException?displayProperty=fullName>, маскируя исходное исключение. В версии .NET Framework 4.7 создается ранее маскированное исключение.

#### <a name="suggestion"></a>Предложение

Если в вашем коде реализуется обработка исключения <xref:System.NullReferenceException?displayProperty=fullName>, измените его для перехвата исключений, которые могут создаваться настраиваемыми действиями.

| Имя    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.7|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

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
