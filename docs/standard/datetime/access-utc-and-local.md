---
title: Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET], retrieving
- time zones [.NET], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
ms.openlocfilehash: b92ac812ed0bd0e80bb3a6ab03b52746eb15db97
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818112"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов

<xref:System.TimeZoneInfo>Класс предоставляет два свойства, <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A> , которые предоставляют коду доступ к предопределенным объектам часового пояса. В этом разделе рассматривается порядок работы с объектами <xref:System.TimeZoneInfo>, возвращаемыми этими свойствами.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Получение объекта TimeZoneInfo времени UTC

1. Используйте `static` свойство ( `Shared` в Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> для доступа к всеобщему скоординированному времени.

2. Вместо того чтобы назначать <xref:System.TimeZoneInfo> объект, возвращаемый свойством, в объектную переменную, продолжайте обращаться к времени в формате UTC через <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство.

### <a name="to-access-the-local-time-zone"></a>Получение местного часового пояса

1. Используйте `static` свойство ( `Shared` в Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> для доступа к часовому поясу локальной системы.

2. Вместо того чтобы назначать <xref:System.TimeZoneInfo> объект, возвращаемый свойством, в объектную переменную, продолжайте обращаться к местному часовому поясу через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство.

## <a name="example"></a>Пример

В следующем коде свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> и <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Необходимо всегда обращаться к локальному часовому поясу через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство, а не назначать местный часовой пояс <xref:System.TimeZoneInfo> переменной объекта. Аналогичным образом следует всегда обращаться к всеобщему скоординированному времени через <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство, не назначив часовой пояс в <xref:System.TimeZoneInfo> объектную переменную. Это предотвращает <xref:System.TimeZoneInfo> недействительность аннулирования переменной объекта при вызове <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метода.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- , Что <xref:System> пространство имен должно быть импортировано с помощью `using` оператора (требуется в коде C#).

## <a name="see-also"></a>См. также статью

- [Даты, время и часовые пояса](index.md)
- [Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md)
- [Как создать объект TimeZoneInfo](instantiate-time-zone-info.md)
