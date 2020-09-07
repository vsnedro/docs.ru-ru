---
ms.openlocfilehash: 04d1c1162dc79bbcb0578c6661466f4d58a57acc
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496301"
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
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Xml.Linq.LoadOptions.SetLineInfo`

-->
