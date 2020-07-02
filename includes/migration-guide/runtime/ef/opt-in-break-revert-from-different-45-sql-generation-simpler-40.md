---
ms.openlocfilehash: 22b5abbe769733e8d5ca3e78dd9e6e13b2363737
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620618"
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
