---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616299"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>Определение рабочего процесса XOML и ключи кэша SqlTrackingService переведены с MD5 на SHA256

#### <a name="details"></a>Подробнее

Среда выполнения рабочих процессов хранит кэш определений рабочих процессов, определенных в XOML. SqlTrackingService также хранит кэш с ключом по строкам. Эти кэши идентифицируются по значениям, которые включают хэш-значение контрольной суммы. В .NET Framework 4.7.2 и более ранних версий для хэширования этой контрольной суммы использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS. Начиная с .NET Framework 4.8 используется алгоритм SHA256. Так как значения вычисляются при каждом запуске среды выполнения рабочих процессов и службы SqlTrackingService, не должно возникнуть проблем совместимости с этим изменением. Тем не менее мы предоставили исправления, чтобы позволить клиентам вернуться к использованию устаревшего алгоритма хэширования при необходимости.

#### <a name="suggestion"></a>Предложение

Если это изменение вызывает проблему при выполнении рабочих процессов, установите для одного или обоих параметров `AppContext`:

- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; значение true.
- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; значение true.
В коде:

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

Или в файле конфигурации (это необходимо сделать в файле конфигурации приложения, который создает объект <xref:System.Workflow.Runtime.WorkflowRuntime>):

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.8         |
| Type    | Изменение целевой платформы |
