---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496760"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Усовершенствования алгоритма выделения пространства для строк со звездами в сетке

#### <a name="details"></a>Подробнее

Исправлена ошибка в [алгоритме выделения размеров для ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) в <xref:System.Windows.Controls.Grid>, представленном в .NET Framework 4.7.  В некоторых случаях, например в сетке с <code>Height=&quot;Auto&quot;</code>, которая содержит пустые строки, строки были расположены в неправильном положении, возможно, даже за пределами сетки.

#### <a name="suggestion"></a>Предложение

Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.8 или более поздней версии.

| name    | Значение       |
|:--------|:------------|
| Область   |Значительно|
|Version|4.8|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
