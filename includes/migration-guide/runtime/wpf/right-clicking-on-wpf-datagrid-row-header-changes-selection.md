---
ms.openlocfilehash: e1faee846627b22b88eb888d6241d47d8ea6ea06
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497395"
---
### <a name="right-clicking-on-a-wpf-datagrid-row-header-changes-the-datagrid-selection"></a>При щелчке правой кнопкой мыши на заголовке строки WPF DataGrid изменяется выделение DataGrid

#### <a name="details"></a>Подробнее

Если щелкнуть правой кнопкой мыши выделенный заголовок строки <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> при наличии нескольких выделенных строк, выделение <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> изменится таким образом, что будет выделена только эта строка.

#### <a name="suggestion"></a>Предложение

Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.DataGrid.%23ctor>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.#ctor`

-->
