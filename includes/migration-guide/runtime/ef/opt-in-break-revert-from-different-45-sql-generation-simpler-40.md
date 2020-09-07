---
ms.openlocfilehash: 346fb6ecd43f7f93529e45f169c79b7acacc9c1f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496940"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Согласие на прерывание для возврата от генерируемого в версии 4.5 кода SQL к более простому коду, генерируемому в версии 4.0

#### <a name="details"></a>Подробнее

Запросы, создающие операторы JOIN и содержащие вызов к операции ограничения без предварительного использования OrderBy, теперь создают более простой код SQL. После обновления до .NET Framework 4.5 эти запросы создают более сложный код SQL, чем предыдущие версии.

#### <a name="suggestion"></a>Предложение

Эта функция отключена по умолчанию. Если Entity Framework создает лишние операторы JOIN, что ведет к ухудшению производительности, можно включить эту функцию, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения (app.config):<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Прозрачный|
|Version|4.5.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
