---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622095"
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
