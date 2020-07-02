---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620709"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>Элементы WPF DataTemplate теперь отображаются в UIA

#### <a name="details"></a>Подробнее

Ранее элементы <xref:System.Windows.DataTemplate?displayProperty=fullName> не отображались в службе автоматизации пользовательского интерфейса. Начиная с версии 4.5, служба автоматизации пользовательского интерфейса будет обнаруживать эти элементы. Это полезно во многих случаях, но может нарушить выполнение тестов, зависящих от деревьев UIA, не содержащих элементы <xref:System.Windows.DataTemplate?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Тесты службы автоматизации пользовательского интерфейса для этого приложения может потребоваться обновить с учетом того, что теперь дерево UIA содержит ранее невидимые элементы <xref:System.Windows.DataTemplate?displayProperty=fullName>. Например, тесты, которые ожидают, что некоторые элементы находятся рядом друг с другом, теперь могут ожидать, что между ними располагаются ранее невидимые элементы UIA. Или может потребоваться обновить новыми значениями тесты, которые зависят от определенных количеств или индексов для UIA элементов.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
