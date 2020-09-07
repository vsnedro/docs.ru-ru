---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497207"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>Каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5 каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора (объекта <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>). При попытке сериализации каталога MEF происходит вызов исключения.

#### <a name="suggestion"></a>Предложение

Больше не следует использовать MEF для создания сериализатора.

| name    | Значение       |
|:--------|:------------|
| Область   |Значительно|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
