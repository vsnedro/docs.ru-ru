---
title: Критическое изменение. Поле TextFormatFlags.ModifyString является устаревшим
description: Сведения о критическом изменении в .NET 5.0, где поле TextFormatFlags.ModifyString является устаревшим
ms.date: 11/05/2020
ms.openlocfilehash: 83dca65a770ccdcd5ce48bb669f5122dc2d5ad77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759681"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a>Флаг TextFormatFlags.ModifyString является устаревшим

Поле <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> устарело в качестве предупреждения и может быть удалено в будущей версии .NET.

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET поле перечисления <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> не помечено как устаревшее. В .NET 5.0 и более поздних версиях оно помечено как устаревшее в качестве предупреждения. Это поле может быть удалено в будущей версии .NET.

## <a name="reason-for-change"></a>Причина изменения

В некоторых ситуациях передача строки в <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> с <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> изменяет строку. Это влечет за собой нарушение неизменности строки и может привести к неустранимому повреждению состояния среды выполнения .NET.

## <a name="version-introduced"></a>Представленная версия

.NET 5.0

## <a name="recommended-action"></a>Рекомендованное действие

Обновите весь код, который зависит от <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->
