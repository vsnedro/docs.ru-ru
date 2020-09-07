---
ms.openlocfilehash: 51ac10e6b4cc9c757cb7f68d7d665982bcb57d4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497499"
---
### <a name="systemactivities-is-now-aptca"></a>System.Activities теперь является атрибутом APTCA

#### <a name="details"></a>Подробнее

Сборка помечена атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Производные классы не могут быть помечены атрибутом <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>. Раньше производные типы должны были быть помечены атрибутом <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>. Однако это изменение не должно иметь никаких реальных последствий.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
