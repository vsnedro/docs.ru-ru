---
ms.openlocfilehash: 56127309c5f5993ffc2e2faedd1f481e8131e094
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400639"
---
### <a name="textformatflagsmodifystring-is-obsolete"></a>Флаг TextFormatFlags.ModifyString является устаревшим

Поле <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> устарело в качестве предупреждения и может быть удалено в будущей версии .NET.

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET поле перечисления <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> не помечено как устаревшее. В .NET 5.0 и более поздних версиях оно помечено как устаревшее в качестве предупреждения. Это поле может быть удалено в будущей версии .NET.

#### <a name="reason-for-change"></a>Причина изменения

В некоторых ситуациях передача строки в <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> с <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> изменяет строку. Это влечет за собой нарушение неизменности строки и может привести к неустранимому повреждению состояния среды выполнения .NET.

#### <a name="version-introduced"></a>Представленная версия

.NET 5.0 RC1

#### <a name="recommended-action"></a>Рекомендованное действие

Обновите весь код, который зависит от <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

-->
