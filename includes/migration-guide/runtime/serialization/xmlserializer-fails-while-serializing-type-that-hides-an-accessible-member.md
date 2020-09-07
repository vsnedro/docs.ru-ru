---
ms.openlocfilehash: 75c7385bceec2595683d1c0d97a7df9264e3bf0b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497298"
---
### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a><span data-ttu-id="79b5a-101">XmlSerializer завершается сбоем при сериализации типа, который скрывает доступный член недоступным</span><span class="sxs-lookup"><span data-stu-id="79b5a-101">XmlSerializer fails while serializing a type that hides an accessible member with an inaccessible one</span></span>

#### <a name="details"></a><span data-ttu-id="79b5a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="79b5a-102">Details</span></span>

<span data-ttu-id="79b5a-103">При сериализации производного типа <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> может завершаться сбоем, если тип содержит недоступное поле или свойство, которое скрывает (посредством ключевого слова "new") ранее доступное поле или свойство с тем же именем (например, public) в базовом типе.</span><span class="sxs-lookup"><span data-stu-id="79b5a-103">When serializing a derived type, the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> can fail if the type contains an inaccessible field or property that hides (via the 'new' keyword) a field or property of the same name that was previously accessible (public, for example) on the base type.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="79b5a-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="79b5a-104">Suggestion</span></span>

<span data-ttu-id="79b5a-105">Чтобы устранить эту проблему, можно сделать новый скрывающий член доступным для <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> (например, для этого можно пометить его как public). Кроме того, можно использовать следующий параметр конфигурации, который возвращает поведение <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> версии 4.0 и устраняет эту проблему:</span><span class="sxs-lookup"><span data-stu-id="79b5a-105">This problem can be solved by making the new, hiding member accessible to the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> (by marking it public, for example).Alternatively, the following config setting will revert to 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> behavior, which will fix the problem:</span></span><pre><code class="lang-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="79b5a-106">name</span><span class="sxs-lookup"><span data-stu-id="79b5a-106">Name</span></span>    | <span data-ttu-id="79b5a-107">Значение</span><span class="sxs-lookup"><span data-stu-id="79b5a-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="79b5a-108">Область</span><span class="sxs-lookup"><span data-stu-id="79b5a-108">Scope</span></span>   |<span data-ttu-id="79b5a-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="79b5a-109">Minor</span></span>|
|<span data-ttu-id="79b5a-110">Version</span><span class="sxs-lookup"><span data-stu-id="79b5a-110">Version</span></span>|<span data-ttu-id="79b5a-111">4.5</span><span class="sxs-lookup"><span data-stu-id="79b5a-111">4.5</span></span>|
|<span data-ttu-id="79b5a-112">Type</span><span class="sxs-lookup"><span data-stu-id="79b5a-112">Type</span></span>|<span data-ttu-id="79b5a-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="79b5a-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="79b5a-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="79b5a-114">Affected APIs</span></span>

- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)`
- `M:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)`

-->
