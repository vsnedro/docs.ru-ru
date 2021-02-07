---
description: 'Дополнительные сведения о: как создать объект TimeZoneInfo'
title: Практическое руководство. Создание экземпляра объекта TimeZoneInfo
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
ms.openlocfilehash: d063833aa60142bf6f942a836c7f89777d9073a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702617"
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a>Практическое руководство. Создание экземпляра объекта TimeZoneInfo

Наиболее распространенный способ создания экземпляра объекта <xref:System.TimeZoneInfo> — получение сведений о нем из реестра. В этом разделе описываются способы создания экземпляра объекта <xref:System.TimeZoneInfo> на основе локального системного реестра.

### <a name="to-instantiate-a-timezoneinfo-object"></a>Создание экземпляра объекта TimeZoneInfo

1. Объявите объект <xref:System.TimeZoneInfo> .

2. Вызовите метод `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> .

3. Обработайте исключения, созданные этим методом, особенно <xref:System.TimeZoneNotFoundException> , создаваемое, если в реестре не определен часовой пояс.

## <a name="example"></a>Пример

Следующий код извлекает объект <xref:System.TimeZoneInfo> , который представляет часовой пояс восточного времени США, и отображает время в этом поясе, соответствующее местному времени.

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

Единственный параметр метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> — идентификатор часового пояса, который необходимо получить и который соответствует свойству <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> объекта. Идентификатор часового пояса — это важнейшее поле, которое уникально идентифицирует часовой пояс. Несмотря на то что большинство ключей являются относительно короткими, идентификатор часового пояса относительно длинный. В большинстве случаев его значение соответствует свойству <xref:System.TimeZoneInfo.StandardName%2A> объекта <xref:System.TimeZoneInfo> , которое используется для предоставления имени стандартного времени часового пояса. Однако существуют исключения. Лучше всего гарантировать, что передается действительный идентификатор, путем перечисления доступных в системе часовых поясов и отслеживания присутствующих в них идентификаторов часовых поясов. Пример см. в разделе [How to: Enumerate time zones present on a computer](enumerate-time-zones.md). Раздел [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) также содержит список идентификаторов избранных часовых поясов.

Если часовой пояс найден, метод возвращает его объект <xref:System.TimeZoneInfo> . Если часовой пояс не найден, метод создает <xref:System.TimeZoneNotFoundException>. Если часовой пояс найден, но его данные повреждены или неполны, метод создает <xref:System.InvalidTimeZoneException>.

Если приложение зависит от наличия часового пояса, необходимо сначала вызвать метод <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для извлечения сведений о часовом поясе из реестра. Если вызов метода завершится сбоем, обработчик исключений должен создать новый экземпляр часового пояса или повторно создать его путем десериализации сериализованного объекта <xref:System.TimeZoneInfo> . Пример см. [в разделе руководство. Восстановление часовых поясов из внедренного ресурса](restore-time-zones-from-an-embedded-resource.md) .

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](index.md)
- [Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md)
- [Как получить доступ к стандартным объектам времени в формате UTC и местному часовому поясу](access-utc-and-local.md)
