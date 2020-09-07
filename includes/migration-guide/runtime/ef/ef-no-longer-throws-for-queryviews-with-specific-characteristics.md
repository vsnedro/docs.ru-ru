---
ms.openlocfilehash: ceae6b85c14862b1b1183d01def0dda723ee0c2b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497600"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>EF более не создает исключения для представлений QueryView с определенными характеристиками

#### <a name="details"></a>Подробнее

Entity Framework больше не создает исключение <xref:System.StackOverflowException?displayProperty=fullName>, если приложение выполняет запрос, включающий представление QueryView со свойством навигации 0..1, которое пытается включить связанные объекты в запрос. Например, это могло быть сделано путем вызова <code>.Include(e =&gt; e.RelatedNavProp)</code>.

#### <a name="suggestion"></a>Предложение

Это изменение влияет только на код, использующий представления QueryView с отношениями 1-0..1 при выполнении запросов, вызывающих метод .Include. Эта функция повышает надежность и должна быть прозрачна почти для всех приложений. Тем не менее, если она вызывает непредвиденное поведение, ее можно отключить, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
