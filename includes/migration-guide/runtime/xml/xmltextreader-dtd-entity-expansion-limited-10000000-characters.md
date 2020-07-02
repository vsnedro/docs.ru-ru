---
ms.openlocfilehash: fdec6671cbf2dae0d72dfaec07f162058b38cf9d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620727"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>Развертывание сущностей DTD XmlTextReader не может превышать 10 000 000 символов

#### <a name="details"></a>Подробнее

Развертывание сущностей DTD теперь не может превышать 10 000 000 символов. Загрузка XML-файлов без развертывания сущностей DTD или с ограниченным развертыванием сущностей DTD не изменяется. Файлы с сущностями DTD, которые развертываются до более чем 10 000 000 символов, не загружаются и теперь вызывают исключение.

#### <a name="suggestion"></a>Предложение

Если ограничение развертывания сущностей DTD существенно ниже 10 000 000, значение может быть переопределено с помощью свойства <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>. <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> с соответствующим значением <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> может передаваться в <code>XmlReader.Create</code>, который принимает <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (т. е. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Xml.XmlTextReader?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)></li></ul>|
