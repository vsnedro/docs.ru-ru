---
title: Источник события BinaryFormatter
description: Узнайте, как использовать источник событий BinaryFormatter для записи событий сериализации или десериализации в журнал.
ms.date: 12/03/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: 9ae2af77b6cfc270207fb0f2969ada8c2eca1153
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740394"
---
# <a name="binaryformatter-event-source"></a>Источник события BinaryFormatter

Начиная с .NET 5.0, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> включает встроенный класс <xref:System.Diagnostics.Tracing.EventSource>, который позволяет реализовать визуализацию данных о сериализации или десериализации объекта. Приложения могут использовать типы, производные от <xref:System.Diagnostics.Tracing.EventListener>, для прослушивания этих уведомлений и их записи в журнал.

Эта функция не заменяет <xref:System.Runtime.Serialization.SerializationBinder> или <xref:System.Runtime.Serialization.ISerializationSurrogate> и не может использоваться для изменения сериализуемых или десериализуемых данных. Напротив, эта система событий предназначена для получения полезных сведений о сериализуемых или десериализуемых типах. Ее также можно использовать для обнаружения нежелательных вызовов к инфраструктуре `BinaryFormatter`, например из кода сторонней библиотеки.

## <a name="description-of-events"></a>Описание событий

Источник событий `BinaryFormatter` имеет известное имя `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`. Прослушиватели могут подписаться на 6 событий.

### <a name="serializationstart-event-id--10"></a>Событие SerializationStart с идентификатором `10`

Возникает при вызове метода <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>, который запускает процесс сериализации. Это событие используется в паре с событием `SerializationEnd`. Событие `SerializationStart` может вызываться рекурсивно, если объект вызывает `BinaryFormatter.Serialize` в своей подпрограмме сериализации.

Это событие не содержит полезных данных.

### <a name="serializationend-event-id--11"></a>Событие SerializationEnd с идентификатором `11`

Возникает, если метод `BinaryFormatter.Serialize` завершил свою работу. Каждое событие `SerializationEnd` указывает на завершение последнего непарного события `SerializationStart`.

Это событие не содержит полезных данных.

### <a name="serializingobject-event-id--12"></a>Событие SerializingObject с идентификатором `12`

Возникает, когда `BinaryFormatter.Serialize` выполняет сериализацию непримитивного типа. Инфраструктура `BinaryFormatter` исключает определенные типы (например, `string` и `int`) и не вызывает это событие при их появлении. Это событие возникает для пользовательских типов и других типов, которые для `BinaryFormatter` не являются собственными.

Такое событие может возникать между событиями `SerializationStart` и `SerializationEnd` или не возникать вовсе.

Это событие содержит полезные данные с одним аргументом:

* `typeName` (`string`): имя сериализуемого типа с указанием сборки (см. статью о <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>).

### <a name="deserializationstart-event-id--20"></a>Событие DeserializationStart с идентификатором `20`

Возникает при вызове метода <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>, который запускает процесс десериализации. Это событие используется в паре с событием `DeserializationEnd`. Событие `DeserializationStart` может вызываться рекурсивно, если объект вызывает `BinaryFormatter.Deserialize` в своей подпрограмме десериализации.

Это событие не содержит полезных данных.

### <a name="deserializationend-event-id--21"></a>Событие DeserializationEnd с идентификатором `21`

Возникает, если метод `BinaryFormatter.Deserialize` завершил свою работу. Каждое событие `DeserializationEnd` указывает на завершение последнего непарного события `DeserializationStart`.

Это событие не содержит полезных данных.

### <a name="deserializingobject-event-id--22"></a>Событие DeserializingObject с идентификатором `22`

Возникает, когда `BinaryFormatter.Deserialize` выполняет десериализацию непримитивного типа. Инфраструктура `BinaryFormatter` исключает определенные типы (например, `string` и `int`) и не вызывает это событие при их появлении. Это событие возникает для пользовательских типов и других типов, которые для `BinaryFormatter` не являются собственными.

Такое событие может возникать между событиями `DeserializationStart` и `DeserializationEnd` или не возникать вовсе.

Это событие содержит полезные данные с одним аргументом.

* `typeName` (`string`): имя десериализуемого типа с указанием сборки (см. статью о <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>).

### <a name="advanced-subscribing-to-a-subset-of-notifications"></a>\[Дополнительно\] Подписка на подмножество уведомлений

Прослушиватели, которым нужно подписаться только на подмножество уведомлений, могут выбрать ключевые слова для добавления.

* `Serialization` = `(EventKeywords)1`: создает события `SerializationStart`, `SerializationEnd` и `SerializingObject`.
* `Deserialization` = `(EventKeywords)2`: создает события `DeserializationStart`, `DeserializationEnd` и `DeserializingObject`.

Если во время регистрации `EventListener` не указать фильтры ключевых слов, будут создаваться все события.

Для получения дополнительной информации см. <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.

## <a name="sample-code"></a>Образец кода

В приведенном ниже коде

- создается производный от `EventListener` тип, который выполняет запись в `System.Console`;
- для этого прослушивателя создается подписка на уведомления, создаваемые `BinaryFormatter`;
- выполняется сериализация и десериализация графа простых объектов с помощью `BinaryFormatter`;
- происходит анализ созданных событий.

:::code language="csharp" source="snippets/binaryformatter-event-source/csharp/Program.cs":::

Выходные данные приведенного выше кода будут примерно следующими:

```output
Event SerializationStart (id=10) received.
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializationStop (id=11) received.
Event DeserializationStart (id=20) received.
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializationStop (id=21) received.
Rehydrated person Logan Edwards
Favorite book: A Tale of Two Cities by Charles Dickens, list price 10.25
```

В этом примере `EventListener` определенной консоли регистрирует, что сначала запускается сериализация, сериализуются экземпляры `Person` и `Book`, а затем сериализация завершается. Аналогичным образом происходит запуск десериализации, десериализуются экземпляры `Person` и `Book`, а затем десериализаця завершается.

Затем приложение выводит значения, содержащиеся в десериализованном экземпляре `Person`, чтобы продемонстрировать, что объект сериализован и десериализован правильно.

## <a name="see-also"></a>См. также раздел

Дополнительные сведения об использовании `EventListener` для получения уведомлений на основе `EventSource` см. в статье о [классе `EventListener`](xref:System.Diagnostics.Tracing.EventListener).
