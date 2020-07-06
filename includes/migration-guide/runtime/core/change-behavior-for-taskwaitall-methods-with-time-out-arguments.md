---
ms.openlocfilehash: 52406f1e4ea4eda417909e52cf6529631cb0ae33
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620564"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>Изменение в поведении методов Task.WaitAll с аргументами времени ожидания

#### <a name="details"></a>Подробнее

В .NET Framework 4.5 реализовано согласованное поведение методов <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>. В .NET Framework 4 поведение этих методов было непоследовательным. По истечении времени ожидания, если одна или несколько задач были завершены или отменены до вызова метода, метод вызывал исключение <xref:System.AggregateException?displayProperty=fullName>. По истечении времени ожидания, если ни одна задача не была завершена или отменена до вызова метода, однако одна или несколько задач входили в эти состояния после вызова метода, метод возвращал значение false.<br/><br/>В .NET Framework 4.5 эти перегрузки метода теперь возвращают false, если все задачи по-прежнему выполняются после истечения времени ожидания, и вызывают исключение <xref:System.AggregateException?displayProperty=fullName>, только если входная задача была отменена (независимо от того, была ли она до или после вызова метода), а никакие другие задачи не выполняются.

#### <a name="suggestion"></a>Предложение

Если исключение <xref:System.AggregateException?displayProperty=fullName> было перехвачено с целью обнаружения задачи, которая была отменена до вызова метода <xref:System.Threading.Tasks.Task.WaitAll%2A>, этот код должен выполнить то же обнаружение с помощью свойства <xref:System.Threading.Tasks.Task.IsCanceled%2A> (например, .Any(t =&gt; t.IsCanceled)), так как .NET Framework 4.6 создаст исключение только в том случае, если все ожидаемые задачи завершены до истечения времени ожидания.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|
