---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616117"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>Атрибут ObsoleteAttribute экспортируется как ObsoleteAttribute и DeprecatedAttribute в сценариях WinMD

#### <a name="details"></a>Подробнее

При создании библиотеки метаданных Windows (WINMD-файл) атрибут <xref:System.ObsoleteAttribute?displayProperty=fullName> экспортируется как <xref:System.ObsoleteAttribute?displayProperty=fullName> и [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).

#### <a name="suggestion"></a>Предложение

При перекомпиляции существующего исходного кода, использующего атрибут <xref:System.ObsoleteAttribute?displayProperty=fullName>, могут выдаваться предупреждения при использовании кода из C++/CX или JavaScript. Не рекомендуется применять атрибуты <xref:System.ObsoleteAttribute?displayProperty=fullName> и [ Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) в коде в управляемых сборках. Это может привести к предупреждениям сборки.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.5.1       |
| Type    | Изменение целевой платформы |
