---
ms.openlocfilehash: 5c8ea3565fbe599dd53a71ba8bd339704f7d7f8a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496526"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Критические изменения в SignedXml и EncryptedXml

#### <a name="details"></a>Подробнее

Исправления системы безопасности в .NET Framework 4.6.2 для <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> и <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> привели к различиям в поведении во время выполнения. Например:<ul><li>Если документ содержит несколько элементов с одинаковым атрибутом <code>id</code>, один из которых является целевым корнем подписи, такой документ будет считаться недействительным.</li><li>Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XPath в ссылках.</li><li>Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XSLT в ссылках.</li><li>Любая программа, использующая удаленные с внешнего ресурса подписи, не сможет сделать это.</li></ul>

#### <a name="suggestion"></a>Предложение

Разработчикам следует изучить, как используются <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> и производные от <xref:System.Security.Cryptography.Xml.Transform> типы, поскольку получатель документа не всегда сможет обработать его.

| Имя    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.Xml.Transform`
- `T:System.Security.Cryptography.Xml.XmlDsigXPathTransform`
- `T:System.Security.Cryptography.Xml.XmlDsigXsltTransform`

-->
