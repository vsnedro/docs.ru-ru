---
title: Взаимное преобразование структур DateTime и DateTimeOffset
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
ms.openlocfilehash: 7607d1d9dfc4f8f286262952599f96e4872db9c9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278224"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Взаимное преобразование структур DateTime и DateTimeOffset

Хотя <xref:System.DateTimeOffset> структура обеспечивает большую степень осведомленности о часовых поясах, чем <xref:System.DateTime> структура, <xref:System.DateTime> Параметры чаще используются в вызовах методов. По этой причине возможность преобразования <xref:System.DateTimeOffset> значений в <xref:System.DateTime> значения и наоборот особенно важна. В этом разделе показано, как выполнять эти преобразования таким образом, чтобы сохранить как можно больше сведений о часовом поясе.

> [!NOTE]
> <xref:System.DateTime>И типы, и <xref:System.DateTimeOffset> имеют некоторые ограничения при представлении времени в часовых поясах. С его <xref:System.DateTime.Kind%2A> свойством <xref:System.DateTime> можно отражать только время в формате UTC и местный часовой пояс системы. <xref:System.DateTimeOffset>отражает смещение времени от времени в формате UTC, но не отражает фактический часовой пояс, к которому относится это смещение. Дополнительные сведения о значениях времени и поддержке часовых поясов см. в разделе [Выбор между DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Преобразование DateTime в DateTimeOffset

<xref:System.DateTimeOffset>Структура предоставляет два эквивалентных способа <xref:System.DateTime> <xref:System.DateTimeOffset> преобразования, которые подходят для большинства преобразований:

- <xref:System.DateTimeOffset.%23ctor%2A>Конструктор, который создает новый <xref:System.DateTimeOffset> объект на основе <xref:System.DateTime> значения.

- Оператор неявного преобразования, который позволяет присвоить <xref:System.DateTime> значение <xref:System.DateTimeOffset> объекту.

Для времени в формате UTC и локальных <xref:System.DateTime> значений <xref:System.DateTimeOffset.Offset%2A> свойство результирующего <xref:System.DateTimeOffset> значения точно отражает время UTC или смещение местного часового пояса. Например, следующий код преобразует время в формате UTC в эквивалентное <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

В этом случае смещение переменной `utcTime2` равняется 00:00. Аналогичным образом следующий код преобразует местное время в эквивалентное ему <xref:System.DateTimeOffset> значение.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Однако для <xref:System.DateTime> значений, <xref:System.DateTime.Kind%2A> свойство которых равно <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> , эти два метода преобразования создают <xref:System.DateTimeOffset> значение, смещение которого равно значению местного часового пояса. Это показано в следующем примере, который выполняется в тихоокеанском стандартном часовом поясе США.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Если <xref:System.DateTime> значение отражает дату и время, отличные от местного часового пояса или времени в формате UTC, можно преобразовать его в <xref:System.DateTimeOffset> значение и сохранить сведения о часовом поясе, вызвав перегруженный <xref:System.DateTimeOffset.%23ctor%2A> конструктор. Например, в следующем примере создается экземпляр <xref:System.DateTimeOffset> объекта, который отражает центральное стандартное время.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Второй параметр для перегруженной версии конструктора, <xref:System.TimeSpan> объект, представляющий смещение времени от UTC, должен быть получен путем вызова метода соответствующего часового <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> пояса. Единственным параметром метода является <xref:System.DateTime> значение, представляющее дату и время, которые необходимо преобразовать. Если часовой пояс поддерживает переход на летнее время, то этот параметр позволяет методу определять соответствующее смещение для конкретных даты и времени.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Преобразование DateTimeOffset в DateTime

<xref:System.DateTimeOffset.DateTime%2A>Свойство чаще всего используется для <xref:System.DateTimeOffset> <xref:System.DateTime> преобразования. Однако он возвращает <xref:System.DateTime> значение <xref:System.DateTime.Kind%2A> , свойство которого равно <xref:System.DateTimeKind.Unspecified> , как показано в следующем примере.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Это означает, что все сведения о <xref:System.DateTimeOffset> связи значения со временем в формате UTC теряются при преобразовании при <xref:System.DateTimeOffset.DateTime%2A> использовании свойства. Это влияет на <xref:System.DateTimeOffset> значения, которые соответствуют времени в формате UTC или по местному времени системы, поскольку <xref:System.DateTimeOffset.DateTime%2A> структура отражает только два часовых пояса в своем <xref:System.DateTime.Kind%2A> свойстве.

Чтобы сохранить как можно больше сведений о часовом поясе при преобразовании в <xref:System.DateTimeOffset> <xref:System.DateTime> значение, можно использовать <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Свойства и <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> .

### <a name="converting-a-utc-time"></a>Преобразование времени в формате UTC

Чтобы указать, что преобразованное <xref:System.DateTimeOffset.DateTime%2A> значение является временем в формате UTC, можно получить значение <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Свойства. Он отличается от <xref:System.DateTimeOffset.DateTime%2A> Свойства двумя способами:

- Он возвращает <xref:System.DateTime> значение, <xref:System.DateTime.Kind%2A> свойство которого равно <xref:System.DateTimeKind.Utc> .

- Если <xref:System.DateTimeOffset.Offset%2A> значение свойства не равно <xref:System.TimeSpan.Zero?displayProperty=nameWithType> , оно преобразует время в формат UTC.

> [!NOTE]
> Если приложению требуется, чтобы преобразованные <xref:System.DateTime> значения однозначно определяли один момент времени, следует использовать <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> свойство для управления всеми <xref:System.DateTimeOffset> <xref:System.DateTime> преобразованиями.

В следующем коде свойство используется <xref:System.DateTimeOffset.UtcDateTime%2A> для преобразования <xref:System.DateTimeOffset> значения, смещение которого равно <xref:System.TimeSpan.Zero?displayProperty=nameWithType> <xref:System.DateTime> значению.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

В следующем коде свойство используется <xref:System.DateTimeOffset.UtcDateTime%2A> для выполнения преобразования часового пояса и преобразования типа для <xref:System.DateTimeOffset> значения.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Преобразование местного времени

Чтобы указать, что <xref:System.DateTimeOffset> значение представляет местное время, можно передать <xref:System.DateTime> значение, возвращаемое <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> свойством, в `static` `Shared` метод (в Visual Basic) <xref:System.DateTime.SpecifyKind%2A> . Метод возвращает дату и время, переданные в нее в качестве первого параметра, но устанавливает <xref:System.DateTime.Kind%2A> свойство в значение, заданное вторым параметром. В следующем коде метод используется <xref:System.DateTime.SpecifyKind%2A> при преобразовании <xref:System.DateTimeOffset> значения, смещение которого соответствует значению местного часового пояса.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

Можно также использовать <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойство для преобразования <xref:System.DateTimeOffset> значения в локальное <xref:System.DateTime> значение. <xref:System.DateTime.Kind%2A>Возвращаемым <xref:System.DateTime> значением является свойство <xref:System.DateTimeKind.Local> . В следующем коде свойство используется <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> при преобразовании <xref:System.DateTimeOffset> значения, смещение которого соответствует значению местного часового пояса.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

При извлечении <xref:System.DateTime> значения с помощью <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойства `get` метод доступа свойства сначала преобразует <xref:System.DateTimeOffset> значение в формат UTC, а затем преобразует его в местное время, вызвав <xref:System.DateTimeOffset.ToLocalTime%2A> метод. Это означает, что можно извлечь значение из свойства, <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> чтобы выполнить преобразование часового пояса одновременно с выполнением преобразования типов. Это также означает, что при выполнении преобразования применяются правила коррекции местного часового пояса. В следующем коде показано использование <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> свойства для выполнения преобразования типа и часового пояса.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Универсальный метод преобразования

В следующем примере определяется метод с именем `ConvertFromDateTimeOffset` , который преобразует <xref:System.DateTimeOffset> значения в <xref:System.DateTime> значения. В зависимости от его смещения он определяет <xref:System.DateTimeOffset> , является ли значение временем в формате UTC, местным временем или другим временем, и соответствующим образом определяет свойство возвращаемого значения даты и времени <xref:System.DateTime.Kind%2A> .

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

В следующем примере вызывается метод `ConvertFromDateTimeOffset` для преобразования значений <xref:System.DateTimeOffset>, представляющих время в формате UTC, местное время и время центрального стандартного часового пояса США.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Обратите внимание, что этот код делает два предположения, которые в зависимости от применения и источника значений даты и времени могут оказаться недопустимыми:

- Предполагается, что значение даты и времени, смещение которого <xref:System.TimeSpan.Zero?displayProperty=nameWithType> представляет время в формате UTC. На самом деле UTC не является временем в определенном часовом поясе, но оно является временем, по отношению к которому стандартизованы времена часовых поясов в мире. Часовые пояса также могут иметь смещение <xref:System.TimeSpan.Zero> .

- Предполагается, что значение даты и времени, смещение для которого равно смещению местного часового пояса, представляет местный часовой пояс. Поскольку значения даты и времени не связаны со своими исходными часовыми поясами, то это может не выполняться. Значение даты и времени может быть создано в другом часовом поясе с тем же самым смещением.

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](index.md)
