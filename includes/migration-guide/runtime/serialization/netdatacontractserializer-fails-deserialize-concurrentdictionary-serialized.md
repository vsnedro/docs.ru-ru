---
ms.openlocfilehash: eef5633ec8566f6d5216b7dca4387766cacb600d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620661"
---
### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a>NetDataContractSerializer не удается выполнить десериализацию ConcurrentDictionary, сериализованного с использованием другой версии .NET

#### <a name="details"></a>Подробнее

По своей структуре <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> может использоваться только при использовании одних и тех же типов CLR на концах сериализации. Таким образом, не гарантируется, что объект, сериализованный в одной версии .NET Framework, может быть десериализован в другой версии платформы.<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> некорректно десериализуется в .NET Framework 4.5.1 или более поздней версии, если сериализация этого типа была выполнена в .NET Framework 4.5 или предшествующих версий.

#### <a name="suggestion"></a>Предложение

Эту проблему можно обойти несколькими способами:<ul><li>Обновите компьютер, на котором выполняется сериализация, до версии .NET Framework 4.5.1.</li><li>Используйте <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> вместо <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>, поскольку он не требует, чтобы на сторонах сериализации и десериализации использовались одинаковые типы CLR .</li><li>Используйте <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> вместо <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>, поскольку в нем не наблюдается это нарушение совместимости между версиями 4.5-&gt;4.5.1.</li></ul>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5.1|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li></ul>|
