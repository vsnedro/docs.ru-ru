---
ms.openlocfilehash: 61749f59f9379a6d18bb013b2612a07cb7822b3a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497748"
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
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.PageRangeSelection`

-->
