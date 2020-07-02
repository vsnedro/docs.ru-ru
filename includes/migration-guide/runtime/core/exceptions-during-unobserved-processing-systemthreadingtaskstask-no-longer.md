---
ms.openlocfilehash: 5ba2ddb76ab946339449246840667ba4a48e9c66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620577"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>Исключения во время обработки без наблюдения в классе System.Threading.Tasks.Task больше не распространяются на поток метода завершения

#### <a name="details"></a>Подробнее

Поскольку класс <xref:System.Threading.Tasks.Task?displayProperty=fullName> представляет асинхронную операцию, он перехватывает все исключения невысокой серьезности, происходящие во время асинхронной обработки. В .NET Framework 4.5, если исключение не наблюдается и код не ожидает задачу, исключение больше не распространяется на поток метода завершения и не приводит к сбою процесса во время сборки мусора. Это изменение повышает надежность приложений, использующих класс Task для выполнения асинхронной обработки без наблюдения.

#### <a name="suggestion"></a>Предложение

Если приложение зависит от асинхронных исключений без наблюдения, распространяющихся на поток метода завершения, можно восстановить прежнее поведение, предоставив соответствующий обработчик для события <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> или задав значение для [элемента конфигурации среды выполнения](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType></li></ul>|
