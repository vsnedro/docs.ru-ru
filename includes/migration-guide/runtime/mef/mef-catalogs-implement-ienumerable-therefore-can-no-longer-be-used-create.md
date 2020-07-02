---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620636"
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
