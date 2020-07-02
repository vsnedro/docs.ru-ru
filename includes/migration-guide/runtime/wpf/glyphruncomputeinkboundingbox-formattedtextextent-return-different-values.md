---
ms.openlocfilehash: 00ffc782c9a15c0d88f797f52372b4658706b350
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620685"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a>Начиная с .NET Framework 4.5 GlyphRun.ComputeInkBoundingBox() и FormattedText.Extent возвращают разные значения

#### <a name="details"></a>Подробнее

В .NET Framework 4.5 были усовершенствованы <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> и <xref:System.Windows.Media.FormattedText.Extent> для решения проблем, когда в некоторых случаях в .NET Framework 4.0 прямоугольники были слишком малы для содержащихся глифов. В результате, начиная с .NET Framework 4.5, некоторые ограничивающие прямоугольники будут иметь больший размер, что приведет к незначительным отличиям в макете пользовательского интерфейса.

#### <a name="suggestion"></a>Предложение

Имейте в виду, что размеры некоторых ограничивающих прямоугольников глифов увеличены. Эти изменения обычно улучшают представление и проверку нахождения в поле. Прежнее (до .NET 4.5) поведение можно восстановить, добавив следующую запись в файл app.config.<pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|
