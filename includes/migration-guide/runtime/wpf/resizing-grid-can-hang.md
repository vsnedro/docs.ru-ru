---
ms.openlocfilehash: 8dc1b4d94d01813a8124d1340b50fa78a9b157f8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496264"
---
### <a name="resizing-a-grid-can-hang"></a>Изменение размеров сетки может привести к зависанию

#### <a name="details"></a>Подробнее

При изменении макета <code>T:System.Windows.Controls.Grid</code> в следующих обстоятельствах может возникать бесконечный цикл:<ul><li>Определения строк содержат два атрибута \*-rows, которые объявляют значения MinHeight и MaxHeight.</li><li>Содержимое \*-rows не превышает ограничение, устанавливаемое соответствующим значением MaxHeight.</li><li>Первое значение MinHeight (плюс любые другие фиксированные или автоматические строки) превышает доступную высоту сетки.</li><li>Приложение предназначено для .NET Framework 4.7 или использует алгоритм выделения версии 4.7, включенный с помощью параметра <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code>.</li></ul>Кроме того, цикл может возникать при наличии более двух строк или в аналогичных случаях для столбцов. Проблема устранена в .Net Framework 4.7.1.

#### <a name="suggestion"></a>Предложение

Выполните обновление до .NET Framework 4.7.1.  Кроме того, если вам не требуется алгоритм выделения версии 4.7, вы можете использовать следующий параметр конфигурации:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| Имя    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
