---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621240"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>Рабочий процесс теперь создает исходное исключение вместо NullReferenceException, которое создавалось в некоторых случаях

#### <a name="details"></a>Подробнее

В .NET Framework 4.6.2 и более ранних версий в тех случаях, когда метод Execute действия рабочего процесса создает исключение со значением <code>null</code> для свойства <xref:System.Exception.Message>, среда выполнения рабочего процесса System.Activities создает исключение <xref:System.NullReferenceException?displayProperty=fullName>, маскируя исходное исключение. В версии .NET Framework 4.7 создается ранее маскированное исключение.

#### <a name="suggestion"></a>Предложение

Если в вашем коде реализуется обработка исключения <xref:System.NullReferenceException?displayProperty=fullName>, измените его для перехвата исключений, которые могут создаваться настраиваемыми действиями.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.7|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
