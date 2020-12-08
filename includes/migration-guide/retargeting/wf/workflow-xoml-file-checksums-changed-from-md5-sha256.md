---
ms.openlocfilehash: b1910bf0338bccd77ad9e983990d4d193698ec1f
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96477684"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a>Контрольные суммы файла XOML рабочего процесса переведены с MD5 на SHA256

#### <a name="details"></a>Подробнее

Для поддержки отладки рабочих процессов на основе XOML с помощью Visual Studio при сборке проектов рабочих процессов, содержащих файлы XOML, контрольная сумма содержимого файла XOML включается в сгенерированный код как значение <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType>. В .NET Framework 4.7.2 и более ранних версий для хэширования этой контрольной суммы использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS. Начиная с .NET Framework 4.8 используется алгоритм SHA256. Для совместимости с WorkflowMarkupSourceAttribute.MD5Digest используются только первые 16 байтов сгенерированной контрольной суммы. Это может приводить к проблемам при отладке. Может потребоваться повторная сборка проекта.

#### <a name="suggestion"></a>Предложение

Если повторная сборка проекта не помогла решить проблему, попробуйте задать для параметра `AppContext`&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; значение true. В коде:

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>

Или в файле конфигурации (это должен быть файл MSBuild.exe.config для используемой программы MSBuild.exe):

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.8         |
| Type    | Изменение целевой платформы |
