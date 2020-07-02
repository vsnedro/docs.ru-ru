---
ms.openlocfilehash: beaac7b14535335a665add4fa056a60793879753
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620673"
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
