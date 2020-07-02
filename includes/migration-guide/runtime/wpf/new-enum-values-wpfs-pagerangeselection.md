---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620702"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a>Новые значения перечисления в перечислении PageRangeSelection WPF

#### <a name="details"></a>Подробнее

Было добавлено два новых члена (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> и <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) в перечисление <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

В большинстве случаев эти изменения не влияют на код пользователя. Однако следует изменить код, зависящий от конкретного числа элементов, существующих в вызовах <xref:System.Enum.GetNames(System.Type)> или <xref:System.Enum.GetValues(System.Type)> к типу <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
