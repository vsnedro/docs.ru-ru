---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496139"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>Свойство CheckForOverflowUnderflow WinForm теперь имеет значение true для System.Drawing

#### <a name="details"></a>Подробнее

Свойство CheckForOverflowUnderflow для сборки System.Drawing.dll имеет значение true.

#### <a name="suggestion"></a>Предложение

Раньше при переполнениях результат усекался без уведомления. Теперь создается исключение <xref:System.OverflowException?displayProperty=fullName>,

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
