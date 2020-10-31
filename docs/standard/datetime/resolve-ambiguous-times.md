---
title: Практическое руководство. Разрешение проблемы неоднозначности времени
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], ambiguous time
- ambiguous time [.NET]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 467153ad1217e529f52bf90262c4264de069ff00
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063525"
---
# <a name="how-to-resolve-ambiguous-times"></a>Практическое руководство. Разрешение проблемы неоднозначности времени

Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC. Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время. При обработке неоднозначного времени можно выполнить одно из следующих действий:

- Сделать предположение о том, насколько время соответствует времени в формате UTC. Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.

- Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.

В этом разделе показано, как устранить неоднозначное время, предполагая, что оно представляет стандартное время часового пояса.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Сопоставление неоднозначного времени стандартному времени часового пояса

1. Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.

2. Если время неоднозначно, вычтите время из <xref:System.TimeSpan> объекта, возвращенного свойством часового пояса <xref:System.TimeZoneInfo.BaseUtcOffset%2A> .

3. Вызовите `static` `Shared` метод (в Visual Basic .NET), <xref:System.DateTime.SpecifyKind%2A> чтобы задать свойству значения даты и времени в формате UTC значение <xref:System.DateTime.Kind%2A> <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .

## <a name="example"></a>Пример

В следующем примере показано, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет стандартное время местного часового пояса.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Пример состоит из метода с именем `ResolveAmbiguousTime` , который определяет, <xref:System.DateTime> является ли передаваемое ему значение неоднозначным. Если значение неоднозначно, метод возвращает <xref:System.DateTime> значение, представляющее соответствующее время в формате UTC. Метод обрабатывает это преобразование, вычитая значение свойства местного часового пояса <xref:System.TimeZoneInfo.BaseUtcOffset%2A> из местного времени.

Как правило, неоднозначное время обрабатывается путем вызова <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> метода для получения массива <xref:System.TimeSpan> объектов, содержащих неоднозначное смещение времени в формате UTC. Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса. <xref:System.TimeZoneInfo.BaseUtcOffset%2A>Свойство возвращает смещение между временем UTC и стандартным временем часового пояса.

В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; местный часовой пояс никогда не назначается объектной переменной. Это рекомендуемый подход, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метода делает недействительными все объекты, которым назначен местный часовой пояс.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- , Что <xref:System> пространство имен должно быть импортировано с помощью `using` оператора (требуется в коде C#).

## <a name="see-also"></a>См. также раздел

- [Даты, время и часовые пояса](index.md)
- [Как разрешить пользователям устранять неоднозначность времени](let-users-resolve-ambiguous-times.md)
