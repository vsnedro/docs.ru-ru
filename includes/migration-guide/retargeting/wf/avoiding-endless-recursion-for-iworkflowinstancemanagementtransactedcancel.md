---
ms.openlocfilehash: ab9431780422dfece5dcf8007d13e6d584f5118f
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96476685"
---
### <a name="avoiding-endless-recursion-for-iworkflowinstancemanagementtransactedcancel-and-iworkflowinstancemanagementtransactedterminate"></a>Предотвращение бесконечной рекурсии для IWorkflowInstanceManagement.TransactedCancel и IWorkflowInstanceManagement.TransactedTerminate

#### <a name="details"></a>Подробнее

В некоторых случаях при использовании API <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedCancel%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedTerminate%2A?displayProperty=nameWithType> для отмены или завершения экземпляра службы рабочего процесса в экземпляре рабочего процесса могло возникать переполнение стека из-за бесконечной рекурсии, когда среда выполнения `Workflow` пыталась сохранить экземпляр службы в ходе обработки запроса. Проблема возникает, если экземпляр рабочего процесса находится в состоянии, когда он ожидает завершения некоторых других необработанных запросов WCF к другой службе. Операции `TransactedCancel` и `TransactedTerminate` создают рабочие элементы, которые помещаются в очередь для экземпляра службы рабочего процесса. Эти рабочие элементы не выполняются в рамках обработки запроса `TransactedCancel/TransactedTerminate`. Поскольку экземпляр службы рабочего процесса занят ожиданием завершения другого необработанного запроса WCF, созданный рабочий элемент остается в очереди. Операция `TransactedCancel/TransactedTerminate` завершается, и управление возвращается клиенту. Если транзакция, связанная с операцией `TransactedCancel/TransactedTerminate`, пытается выполнить фиксацию, ей требуется сохранить состояние экземпляра службы рабочего процесса. Однако из-за наличия незавершенного запроса `WCF` для экземпляра среда выполнения рабочего процесса не может сохранить экземпляр службы рабочего процесса, и бесконечный цикл рекурсии приводит к переполнению стека. Поскольку `TransactedCancel` и `TransactedTerminate` создают рабочий элемент только в памяти, тот факт, что транзакция существует, не оказывает никакого влияния. Откат транзакции не приводит к отмене рабочего элемента. Чтобы устранить эту проблему, начиная с .NET Framework 4.7.2 мы представили `AppSetting`, который можно добавлять в `web.config/app.config` службы рабочего процесса, чтобы указать на необходимость пропуска транзакций для `TransactedCancel` и `TransactedTerminate`. Это обеспечивает фиксацию транзакции без ожидания сохранения экземпляра рабочего процесса. Параметр AppSetting для этой возможности называется `microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate`. Значение `true` указывает, что транзакцию следует игнорировать, что позволяет избежать переполнения стека. Значение по умолчанию этого AppSetting — `false`, поэтому существующие экземпляры службы рабочих процессов не затрагиваются.

#### <a name="suggestion"></a>Предложение

При использовании AppFabric или другого клиента <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> и возникновении переполнения стека в экземпляре службы рабочего процесса при попытке отменить или завершить экземпляр рабочего процесса можно добавить следующий код в раздел `<appSettings>` файла web.config/app.config для службы рабочего процесса:

<pre><code class="lang-xml">&lt;add key=&quot;microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate&quot; value=&quot;true&quot;/&gt;&#13;&#10;</code></pre>

Если проблема не возникает, этого делать не нужно.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |
