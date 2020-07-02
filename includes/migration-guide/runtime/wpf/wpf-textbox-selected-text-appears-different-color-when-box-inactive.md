---
ms.openlocfilehash: cd59818fe674e10a206725bea8a74c4aceed99b1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620708"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>Выделенный текст в элементе управления TextBox WPF будет отображаться другим цветом, если текстовое поле неактивно

#### <a name="details"></a>Подробнее

В .NET Framework 4.5, если элемент управления текстовым полем WPF неактивен (в нем отсутствует фокус), выбранный текст внутри поля будет отображаться цветом, отличным от того, когда элемент управления является активным.

#### <a name="suggestion"></a>Предложение

Чтобы восстановить прежнее поведение (.NET Framework 4.0), задайте для свойства <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> значение <code>false</code>.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
