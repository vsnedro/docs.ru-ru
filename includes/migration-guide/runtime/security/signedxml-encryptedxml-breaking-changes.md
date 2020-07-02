---
ms.openlocfilehash: 8cc4f2ba2923774ef4e4e6861a89a7797ca988e1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621203"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Критические изменения в SignedXml и EncryptedXml

#### <a name="details"></a>Подробнее

Исправления системы безопасности в .NET Framework 4.6.2 для <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> и <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> привели к различиям в поведении во время выполнения. Например:<ul><li>Если документ содержит несколько элементов с одинаковым атрибутом <code>id</code>, один из которых является целевым корнем подписи, такой документ будет считаться недействительным.</li><li>Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XPath в ссылках.</li><li>Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XSLT в ссылках.</li><li>Любая программа, использующая удаленные с внешнего ресурса подписи, не сможет сделать это.</li></ul>

#### <a name="suggestion"></a>Предложение

Разработчикам следует изучить, как используются <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> и производные от <xref:System.Security.Cryptography.Xml.Transform> типы, поскольку получатель документа не всегда сможет обработать его.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.2|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|
