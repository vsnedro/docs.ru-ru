---
title: Практическое руководство. Перечисление присутствующих на компьютере часовых поясов
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], enumerating
- enumerating time zones [.NET]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
ms.openlocfilehash: 276c13bb95685e9588e25238f1a6e45cd57a6c91
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817969"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Практическое руководство. Перечисление присутствующих на компьютере часовых поясов

Для успешной работы с указанным часовым поясом необходимо, чтобы сведения об этом часовом поясе были доступны в системе. В операционных системах Windows XP и Windows Vista эти сведения хранятся в реестре. Тем не менее, хотя общее число часовых поясов, которые существуют по всему миру, велико, реестр содержит сведения только о подмножестве из них. Кроме того, реестр сам является динамической структурой, содержимое которой подвержено преднамеренным и случайным изменениям. В итоге приложение не может всегда предполагать, что конкретный часовой пояс определен и доступен в системе. Первым шагом для многих приложений, использующих данные о часовых поясах, является определение доступности требуемого часового пояса на локальном компьютере или предоставление пользователю списка часовых поясов для выбора. Для этого необходимо, чтобы приложение перечислило часовые пояса, определенные в локальной системе.

> [!NOTE]
> Если приложение полагается на присутствие определенного часового пояса, которое не может быть определено в локальной системе, приложение может обеспечить его присутствие путем сериализации и десериализации сведений о часовом поясе. Затем часовой пояс можно добавить в элемент управления "список", чтобы пользователь приложения мог выбрать его. Дополнительные сведения см. [в разделе как сохранить Часовые пояса во внедренном ресурсе](save-time-zones-to-an-embedded-resource.md) и [как восстановить Часовые пояса из внедренного ресурса](restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Перечисление часовых поясов, присутствующих в локальной системе

1. Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. Метод возвращает универсальную <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов. Записи в коллекции сортируются по их <xref:System.TimeZoneInfo.DisplayName%2A> свойству. Пример:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Перечисляет отдельные <xref:System.TimeZoneInfo> объекты в коллекции с помощью `foreach` цикла (в C#) или `For Each` ...`Next` цикл (в Visual Basic) и выполните необходимую обработку для каждого объекта. Например, следующий код перечисляет <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов, возвращенных на шаге 1, и отображает отображаемое имя каждого часового пояса в консоли.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Предоставление пользователю списка часовых поясов, имеющихся в локальной системе

1. Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. Метод возвращает универсальную <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов.

2. Назначьте коллекцию, возвращенную в шаге 1, `DataSource` свойству элемента управления Windows Forms или ASP.NET List.

3. Получение <xref:System.TimeZoneInfo> объекта, выбранного пользователем.

В примере показана Иллюстрация для приложения Windows.

## <a name="example"></a>Пример

В примере запускается приложение Windows, которое отображает Часовые пояса, определенные в системе, в поле со списком. Затем в примере отображается диалоговое окно, содержащее значение <xref:System.TimeZoneInfo.DisplayName%2A> свойства объекта часового пояса, выбранного пользователем.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Большинство элементов управления "список" (например, <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> или <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> ) позволяют назначить коллекцию переменных объекта их `DataSource` свойству, если эта коллекция реализует <xref:System.Collections.IEnumerable> интерфейс. ( <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Это делается универсальным классом.) Чтобы отобразить отдельный объект в коллекции, элемент управления вызывает `ToString` метод объекта для извлечения строки, используемой для представления объекта. В случае с <xref:System.TimeZoneInfo> объектами `ToString` метод возвращает <xref:System.TimeZoneInfo> Отображаемое имя объекта (значение его <xref:System.TimeZoneInfo.DisplayName%2A> Свойства).

> [!NOTE]
> Поскольку элементы управления "список" вызывают `ToString` метод объекта, можно присвоить <xref:System.TimeZoneInfo> элементу управления коллекцию объектов, отображать для каждого объекта понятное имя и получать <xref:System.TimeZoneInfo> объект, выбранный пользователем. Это избавляет от необходимости извлекать строку для каждого объекта в коллекции, присваивать строку коллекции, которая в свою очередь назначена `DataSource` свойству элемента управления, получать строку, выбранную пользователем, а затем использовать эту строку для извлечения объекта, который он описывает.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Для импорта следующих пространств имен:

  <xref:System> (в коде C#)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>См. также статью

- [Даты, время и часовые пояса](index.md)
- [Как сохранять Часовые пояса во внедренном ресурсе](save-time-zones-to-an-embedded-resource.md)
- [Как восстановить Часовые пояса из внедренного ресурса](restore-time-zones-from-an-embedded-resource.md)
