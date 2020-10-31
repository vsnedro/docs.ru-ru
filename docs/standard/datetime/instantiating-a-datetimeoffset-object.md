---
title: Создание экземпляра объекта DateTimeOffset
description: Узнайте, как создать объект DateTimeOffset в .NET (создать экземпляр). Сведения о дате & литералах времени, конструкторах, неявном преобразовании типов, & других.
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
ms.openlocfilehash: 4158a3d3bbd7ada87dd0c773cf9a0f5e001ad918
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063629"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Создание экземпляра объекта DateTimeOffset

<xref:System.DateTimeOffset>Структура предлагает несколько способов создания новых <xref:System.DateTimeOffset> значений. Многие из них непосредственно соответствуют методам, доступным для создания новых <xref:System.DateTime> значений, с улучшенными возможностями, которые позволяют указать смещение значения даты и времени относительно времени в формате UTC. В частности, можно создать экземпляр <xref:System.DateTimeOffset> значения следующими способами.

- С помощью литерала даты и времени.

- Путем вызова <xref:System.DateTimeOffset> конструктора.

- Путем неявного преобразования значения в <xref:System.DateTimeOffset> значение.

- Разбором строкового представления даты и времени.

В этом разделе приводятся более подробные сведения и примеры кода, иллюстрирующие эти методы создания экземпляров новых <xref:System.DateTimeOffset> значений.

## <a name="date-and-time-literals"></a>Литералы даты и времени

Для языков, поддерживающих эту возможность, одним из наиболее распространенных способов создания <xref:System.DateTime> значения является предоставление даты и времени в виде жестко запрограммированного литерального значения. Например, следующий код Visual Basic создает <xref:System.DateTime> объект, значение которого равно 1 января 2008 г., в 10:00 AM.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset> значения также можно инициализировать с помощью литералов даты и времени при использовании языков, поддерживающих <xref:System.DateTime> литералы. Например, следующий код Visual Basic создает <xref:System.DateTimeOffset> объект.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Как видно из выходных данных консоли, <xref:System.DateTimeOffset> создаваемому таким образом значению назначается смещение местного часового пояса. Это означает, что <xref:System.DateTimeOffset> значение, назначенное с помощью символьного литерала, не определяет единственный момент времени, если код выполняется на разных компьютерах.

## <a name="datetimeoffset-constructors"></a>Конструкторы DateTimeOffset

<xref:System.DateTimeOffset>Тип определяет шесть конструкторов. Четыре из них непосредственно соответствуют <xref:System.DateTime> конструкторам с дополнительным параметром типа <xref:System.TimeSpan> , который определяет смещение даты и времени относительно времени в формате UTC. Они позволяют определить <xref:System.DateTimeOffset> значение на основе значений отдельных компонентов даты и времени. Например, следующий код использует эти четыре конструктора для создания экземпляров <xref:System.DateTimeOffset> объектов с одинаковыми значениями 7/1/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Обратите внимание, что, когда значение <xref:System.DateTimeOffset> объекта, созданного с помощью <xref:System.Globalization.PersianCalendar> объекта в качестве одного из аргументов конструктора, отображается в консоли, оно выражается как дата в григорианском, а не в персидском календаре. Чтобы вывести дату в персидском календаре, см. пример в <xref:System.Globalization.PersianCalendar> разделе.

Два других конструктора создают <xref:System.DateTimeOffset> объект на основе <xref:System.DateTime> значения. Первый из них имеет один параметр — <xref:System.DateTime> значение для преобразования в <xref:System.DateTimeOffset> значение. Смещение результирующего <xref:System.DateTimeOffset> значения зависит от <xref:System.DateTime.Kind%2A> Свойства единственного параметра конструктора. Если его значение равно <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , то смещение устанавливается равным <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . В противном случае его смещение приравнивается к смещению местного часового пояса. В следующем примере показано использование этого конструктора для создания экземпляров объектов, <xref:System.DateTimeOffset> представляющих время в формате UTC и местного часового пояса:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Вызов перегрузки <xref:System.DateTimeOffset> конструктора, имеющего один <xref:System.DateTime> параметр, эквивалентен выполнению неявного преобразования <xref:System.DateTime> значения в <xref:System.DateTimeOffset> значение.

Второй конструктор, создающий <xref:System.DateTimeOffset> объект из <xref:System.DateTime> значения, имеет два параметра: <xref:System.DateTime> преобразуемое значение и <xref:System.TimeSpan> значение, представляющее смещение даты и времени относительно времени в формате UTC. Это значение смещения должно соответствовать <xref:System.DateTime.Kind%2A> свойству первого параметра конструктора или <xref:System.ArgumentException> порождается исключение. Если <xref:System.DateTime.Kind%2A> свойство первого параметра имеет <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> значение, то значением второго параметра должно быть <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . Если <xref:System.DateTime.Kind%2A> свойство первого параметра имеет <xref:System.DateTimeKind.Local?displayProperty=nameWithType> значение, то значением второго параметра должно быть смещение часового пояса локальной системы. Если <xref:System.DateTime.Kind%2A> свойство первого параметра имеет <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> значение, то смещение может быть любым допустимым значением. Следующий код иллюстрирует вызовы этого конструктора для преобразования <xref:System.DateTime> в <xref:System.DateTimeOffset> значения.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Неявное преобразование типов

<xref:System.DateTimeOffset>Тип поддерживает одно неявное преобразование типа: из <xref:System.DateTime> значения в <xref:System.DateTimeOffset> значение. (Неявное преобразование типов — это преобразование одного типа в другой, не требующее явного приведения, как в языке C#, или преобразования, как в языке Visual Basic, в ходе которого не теряются данные.) Благодаря этому можно использовать код, аналогичный приведенному ниже.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

Смещение результирующего <xref:System.DateTimeOffset> значения зависит от <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> значения свойства. Если его значение равно <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , то смещение устанавливается равным <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . Если его значение равно <xref:System.DateTimeKind.Local?displayProperty=nameWithType> или <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> , то смещение устанавливается равным значению местного часового пояса.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Анализ строкового представления даты и времени

<xref:System.DateTimeOffset>Тип поддерживает четыре метода, позволяющие преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значение:

- <xref:System.DateTimeOffset.Parse%2A>, который пытается преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значение и создает исключение, если преобразование выполнить не удается.

- <xref:System.DateTimeOffset.TryParse%2A>, который пытается преобразовать строковое представление даты и времени в <xref:System.DateTimeOffset> значение и возвращает, `false` Если преобразование завершается неудачей.

- <xref:System.DateTimeOffset.ParseExact%2A>, который пытается преобразовать строковое представление даты и времени в указанном формате в <xref:System.DateTimeOffset> значение. Этот метод создает исключение при сбое преобразования.

- <xref:System.DateTimeOffset.TryParseExact%2A>, который пытается преобразовать строковое представление даты и времени в указанном формате в <xref:System.DateTimeOffset> значение. При сбое преобразования метод возвращает значение `false`.

В следующем примере показаны вызовы каждого из этих четырех методов преобразования строк для создания экземпляра <xref:System.DateTimeOffset> значения.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>См. также раздел

- [Даты, время и часовые пояса](index.md)
