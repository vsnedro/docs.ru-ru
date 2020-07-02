---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620696"
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
