---
title: Практическое руководство. Создание часовых поясов с правилами коррекции
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
ms.openlocfilehash: b7e938581dfde3f1566aa2506302292686c2fc5c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278172"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Практическое руководство. Создание часовых поясов с правилами коррекции

Точные сведения о часовом поясе, необходимые для приложения, могут отсутствовать в определенной системе по нескольким причинам:

- Часовой пояс никогда не был определен в реестре локальной системы.

- Данные о часовом поясе были изменены или удалены из реестра.

- Часовой пояс не содержит точных сведений о корректировках часового пояса для определенного исторического периода.

В таких случаях можно вызвать <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод, чтобы определить часовой пояс, необходимый для приложения. Перегрузки этого метода можно использовать для создания часового пояса с правилами коррекции или без них. Если часовой пояс поддерживает переход на летнее время, можно определить корректировки с помощью фиксированных или плавающих правил коррекции. (Определения этих терминов см. в подразделе «терминология часовых поясов» раздела « [Общие сведения о часовом поясе](time-zone-overview.md)».)

> [!IMPORTANT]
> Пользовательские часовые пояса, созданные путем вызова <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода, не добавляются в реестр. Вместо этого доступ к ним можно получить только через ссылку на объект, возвращенную <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> вызовом метода.

В этом разделе показано, как создать часовой пояс с правилами коррекции. Сведения о создании часового пояса, не поддерживающего правила коррекции перехода на летнее время, см. [в разделе как создавать Часовые пояса без правил коррекции](create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Создание часового пояса с плавающими правилами коррекции

1. Для каждой корректировки (т. е. для каждого перехода на зимнее и обратное время в течение определенного интервала времени) выполните следующие действия.

    1. Определите начальное время перехода для коррекции часового пояса.

       Необходимо вызвать <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> метод и передать ему <xref:System.DateTime> значение, определяющее время перехода, целочисленное значение, определяющее месяц перехода, целочисленное значение, определяющее неделю перехода, и <xref:System.DayOfWeek> значение, определяющее день недели, в который происходит переход. Этот вызов метода создает экземпляр <xref:System.TimeZoneInfo.TransitionTime> объекта.

    2. Укажите время окончания перехода для коррекции часового пояса. Для этого требуется еще один вызов <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> метода. Этот вызов метода создает экземпляр второго <xref:System.TimeZoneInfo.TransitionTime> объекта.

    3. Вызовите <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> метод и передайте ему действующие даты начала и окончания корректировки, <xref:System.TimeSpan> объект, определяющий время перехода, и два <xref:System.TimeZoneInfo.TransitionTime> объекта, которые определяют, когда происходят переходы на летнее время и обратно. Этот вызов метода создает экземпляр <xref:System.TimeZoneInfo.AdjustmentRule> объекта.

    4. Назначьте <xref:System.TimeZoneInfo.AdjustmentRule> объект массиву <xref:System.TimeZoneInfo.AdjustmentRule> объектов.

2. Определите отображаемое имя часового пояса. Отображаемое имя соответствует довольно стандартному формату, в котором смещение часового пояса относительно времени в формате UTC заключено в круглые скобки. за ним следует строка, определяющая часовой пояс, один или несколько городов в часовом поясе, а также одну или несколько стран или регионов в часовом поясе.

3. Определите имя стандартного времени часового пояса. Как правило, эта строка также используется в качестве идентификатора часового пояса.

4. Определите название часового пояса (лето).

5. Если вы хотите использовать другой идентификатор, отличный от стандартного имени часового пояса, определите идентификатор часового пояса.

6. Создайте экземпляр <xref:System.TimeSpan> объекта, который определяет смещение часового пояса относительно времени в формате UTC. Часовые пояса со временем, превышающим время UTC, имеют положительное смещение. Часовые пояса со временем, предшествующим UTC, имеют отрицательное смещение.

7. Вызовите <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> метод, чтобы создать экземпляр нового часового пояса.

## <a name="example"></a>Пример

В следующем примере определяется центральный стандартный часовой пояс для США, включающий правила коррекции для различных временных интервалов от 1918 до текущего.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

Часовой пояс, созданный в этом примере, имеет несколько правил коррекции. Необходимо соблюдать осторожность, чтобы гарантировать, что действующие даты начала и окончания всех правил коррекции не перекрываются с датами другого правила коррекции. Если перекрывается, <xref:System.InvalidTimeZoneException> создается исключение.

Для правил коррекции с плавающей запятой значение 5 передается в `week` параметр <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> метода, чтобы указать, что переход выполняется в последнюю неделю конкретного месяца.

При создании массива <xref:System.TimeZoneInfo.AdjustmentRule> объектов для использования в <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> вызове метода код может инициализировать массив до размера, необходимого для количества корректировок, создаваемых для часового пояса. Вместо этого этот пример кода вызывает <xref:System.Collections.Generic.List%601.Add%2A> метод, чтобы добавить каждое правило коррекции в универсальную <xref:System.Collections.Generic.List%601> коллекцию <xref:System.TimeZoneInfo.AdjustmentRule> объектов. Затем код вызывает метод, <xref:System.Collections.Generic.List%601.CopyTo%2A> чтобы скопировать члены этой коллекции в массив.

В примере также используется <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> метод для определения корректировок фиксированной даты. Это похоже на вызов <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> метода, за исключением того, что ему требуется только время, месяц и день параметров перехода.

Пример можно протестировать с помощью следующего кода:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Для импорта следующих пространств имен:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](index.md)
- [Общие сведения о часовых поясах](time-zone-overview.md)
- [Практическое руководство. Создание часовых поясов без правил коррекции](create-time-zones-without-adjustment-rules.md)
