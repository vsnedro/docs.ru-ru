---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620714"
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
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
