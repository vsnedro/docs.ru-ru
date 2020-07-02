---
ms.openlocfilehash: 5c27e8acdf30533036546ba4cca9e06877bde362
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620733"
---
### <a name="xslt-style-sheet-exception-message-changed"></a>Изменено сообщение об исключении таблицы стилей XSLT

#### <a name="details"></a>Подробнее

В .NET Framework 4.5 текст сообщения об ошибке, вызванной тем, что XSLT-файл является слишком сложным, выглядит так: &quot;Слишком сложная таблица стилей&quot;. В предыдущих версиях сообщение об ошибке имело вид &quot;Ошибка компиляции XSLT&quot;. Код приложений, который зависит от текста сообщения об ошибке, больше не будет работать. Однако типы исключений остаются теми же, поэтому это изменение не должно иметь никаких реальных последствий.

#### <a name="suggestion"></a>Предложение

Обновите код приложения, зависящий от сообщения об исключении из этого условия ошибки, для ожидания нового сообщения или (что еще лучше) обновите код так, чтобы он зависел только от типа исключения (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), который не изменился.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
