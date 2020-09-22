---
ms.openlocfilehash: 7d7424b3ca0d295022999e95ed9862b5226b6220
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606169"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>Атрибут ObsoleteAttribute экспортируется как ObsoleteAttribute и DeprecatedAttribute в сценариях WinMD

#### <a name="details"></a>Подробнее

При создании библиотеки метаданных Windows (WINMD-файл) атрибут <xref:System.ObsoleteAttribute?displayProperty=fullName> экспортируется как <xref:System.ObsoleteAttribute?displayProperty=fullName> и [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute).

#### <a name="suggestion"></a>Предложение

При перекомпиляции существующего исходного кода, использующего атрибут <xref:System.ObsoleteAttribute?displayProperty=fullName>, могут выдаваться предупреждения при использовании кода из C++/CX или JavaScript. Не рекомендуется применять атрибуты <xref:System.ObsoleteAttribute?displayProperty=fullName> и [ Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) в коде в управляемых сборках. Это может привести к предупреждениям сборки.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.5.1       |
| Type    | Изменение целевой платформы |
