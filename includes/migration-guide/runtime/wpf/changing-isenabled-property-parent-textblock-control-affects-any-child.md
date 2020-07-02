---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621263"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>Изменение свойства IsEnabled для родительского объекта элемента управления TextBlock влияет на любые дочерние элементы управления

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.6.2, изменение свойства <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> родительского объекта элемента управления <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> влияет на любые дочерние элементы управления (например, гиперссылки и кнопки) элемента <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>. В .NET Framework 4.6.1 и более ранних версий элементы управления внутри элемента <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> не всегда отражали состояние свойства <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> родительского объекта <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Нет. Это изменение соответствует ожидаемому поведению для элементов управления, содержащихся внутри элемента управления <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.2|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
