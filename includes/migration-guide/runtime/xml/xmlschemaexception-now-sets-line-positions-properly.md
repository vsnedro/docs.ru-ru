---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620726"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>Свойство XmlSchemaException теперь правильно задает позиции строк

#### <a name="details"></a>Подробнее

Если значение <xref:System.Xml.Linq.LoadOptions.SetLineInfo> передается методу Load и возникает ошибка проверки, свойства <xref:System.Xml.Schema.XmlSchemaException.LineNumber> и <xref:System.Xml.Schema.XmlSchemaException.LinePosition> теперь содержат сведения о строке.

#### <a name="suggestion"></a>Предложение

Код обработки исключений, который предполагает, что свойства <xref:System.Xml.Schema.XmlSchemaException.LineNumber> и <xref:System.Xml.Schema.XmlSchemaException.LinePosition> не будут задаваться, необходимо обновить, поскольку эти свойства теперь задаются правильно при использовании SetLineInfo во время загрузки XML.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
