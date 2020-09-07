---
ms.openlocfilehash: 9d960774161fc44810f90ca30f56eb98f98de3ff
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496907"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>Ограничение отмены по умолчанию для текстового поля WPF равно 100

#### <a name="details"></a>Подробнее

В .NET Framework 4.5 ограничение отмены по умолчанию для текстового поля WPF равно 100 (в отличие от неограниченного в .NET Framework 4.0)

#### <a name="suggestion"></a>Предложение

Если ограничение отмены, равное 100, слишком низкое, ограничение можно задать явным образом с помощью свойства <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
