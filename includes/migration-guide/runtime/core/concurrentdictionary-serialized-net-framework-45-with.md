---
ms.openlocfilehash: 450bfc56c99a3df9be71be2ef7df6e4e12d4ed76
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496700"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>Объект ConcurrentDictionary, сериализованный в .NET Framework 4.5 с помощью NetDataContractSerializer, нельзя десериализовать в .NET Framework 4.5.1 или 4.5.2

#### <a name="details"></a>Подробнее

Из-за внутренних изменений типа объекты <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, сериализованные в .NET Framework 4.5 с помощью <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>, не могут быть десериализованы в .NET Framework 4.5.1 или .NET Framework 4.5.2. Обратите внимание, что сериализация в .NET Framework 4.5.x с последующей десериализацией в .NET Framework 4.5 будет работать нормально. Аналогичным образом, сериализация в версиях 4.x работает в .NET Framework 4.6. Сериализация и десериализация в одной версии платформы .NET Framework не затрагивается.

#### <a name="suggestion"></a>Предложение

Если требуется выполнить сериализацию и десериализацию объектов <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> между версиями .NET Framework 4.5 и .NET Framework 4.5.1/4.5.2, следует использовать альтернативный сериализатор, например <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> или <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName>, вместо <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>. Кроме того, поскольку эта проблема была устранена в .NET Framework 4.6, она может быть решена путем обновления до этой версии платформы .NET Framework.

| Имя    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
