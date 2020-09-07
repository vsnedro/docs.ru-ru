---
ms.openlocfilehash: 71cc7119710a2b381626dd9cf4ab66265eb3deba
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497233"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>Классу SoapFormatter не удается выполнить десериализацию хэш-таблицы и подобных упорядоченных объектов коллекции

#### <a name="details"></a>Подробнее

Класс <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> не гарантирует, что объекты, сериализованные в одной версии .NET Framework, будут успешно десериализованы в другой версии платформы. В частности, в некоторые упорядоченные коллекции (например, <xref:System.Collections.Hashtable?displayProperty=fullName>) добавлены элементы в версиях с 4.0 по 4.5, поэтому объекты этих типов не могут быть десериализованы в .NET Framework 4.0, если бы они были сериализованы в .NET Framework 4.5. Обратите внимание, что если сериализованные данные сериализуются и десериализуются в одной версии .NET Framework, проблемы не возникают.

#### <a name="suggestion"></a>Предложение

Чтобы обеспечить поддержку изменений в .NET Framework, сериализацию <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> следует заменить на сериализацию <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> или <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
