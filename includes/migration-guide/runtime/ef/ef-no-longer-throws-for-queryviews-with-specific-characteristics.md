---
ms.openlocfilehash: c6c897c13c84ce4b2be21da18e5702365518f286
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620625"
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
