---
ms.openlocfilehash: 7ac0cac53ab2fa7657d0ae58f11d9e777631acc9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620691"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>Доступ к выделенным элементам DataGrid WPF из события UnloadingRow DataGrid может привести к исключению NullReferenceException

#### <a name="details"></a>Подробнее

Из-за ошибки в .NET Framework 4.5 обработчики событий <xref:System.Windows.Controls.DataGrid>, которые выполняют удаление строки, могут привести к созданию исключения <xref:System.NullReferenceException?displayProperty=fullName> при попытке получить доступ к свойствам <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> или <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName><xref:System.Windows.Controls.DataGrid>.

#### <a name="suggestion"></a>Предложение

Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
