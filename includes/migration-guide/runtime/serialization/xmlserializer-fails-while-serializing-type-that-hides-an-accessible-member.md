---
ms.openlocfilehash: eafbdd2d42977381fb4d77748a3c9a2595ff2936
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620655"
---
### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a>XmlSerializer завершается сбоем при сериализации типа, который скрывает доступный член недоступным

#### <a name="details"></a>Подробнее

При сериализации производного типа <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> может завершаться сбоем, если тип содержит недоступное поле или свойство, которое скрывает (посредством ключевого слова "new") ранее доступное поле или свойство с тем же именем (например, public) в базовом типе.

#### <a name="suggestion"></a>Предложение

Чтобы устранить эту проблему, можно сделать новый скрывающий член доступным для <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> (например, для этого можно пометить его как public). Кроме того, можно использовать следующий параметр конфигурации, который возвращает поведение <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> версии 4.0 и устраняет эту проблему:<pre><code class="lang-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType></li></ul>|
