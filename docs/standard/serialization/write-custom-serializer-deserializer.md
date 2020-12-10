---
title: Написание пользовательских сериализаторов и десериализаторов с помощью System.Text.Json
description: Узнайте, как создавать пользовательские сериализаторы и десериализаторы для JSON с помощью пространства имен System.Text.Json.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: a01d3c8dd18c114ea1c3aabc402bc841a6025ffe
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439861"
---
# <a name="how-to-write-custom-serializers-and-deserializers-with-no-locsystemtextjson"></a>Написание пользовательских сериализаторов и десериализаторов с помощью System.Text.Json

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это последовательный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` или `ReadOnlySequence<byte>` с высокой производительностью и низким уровнем распределения. `Utf8JsonReader` — это низкоуровневый тип, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы. Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записать текст JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`. Модуль записи — это низкоуровневый тип, с помощью которого можно создавать пользовательские сериализаторы. Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модели DOM только для чтения с помощью `Utf8JsonReader`. Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON. Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>. Тип `JsonElement` предоставляет перечислители массивов и объектов вместе с API-интерфейсами для преобразования текста JSON в стандартные типы .NET. `JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.

В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.

## <a name="use-jsondocument-for-access-to-data"></a>Использование класса JsonDocument для доступа к данным

В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным в строке JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades1":::

Предыдущий код:

* Предполагается, что анализируемый код JSON находится в строке `jsonString`.
* Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.
* Назначает значение по умолчанию 70 для учащихся, у которых нет оценки.
* Подсчитывает число учащихся путем увеличения переменной `count` с каждой итерацией. Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, как показано в следующем примере:

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades2":::

Ниже приведен пример JSON, обрабатываемый этим кодом:

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-jsondocument-to-write-json"></a>Использование класса JsonDocument для записи кода JSON

В следующем примере показано, как записать JSON код из <xref:System.Text.Json.JsonDocument>.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs" id="Serialize":::

Предыдущий код:

* Считывает JSON-файл, загружает данные в `JsonDocument` и записывает форматированный (структурированный) код JSON в файл.
* Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входных данных JSON разрешены, но пропускаются.
* По завершении для модуля записи вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>. В качестве альтернативы можно разрешить автоматическую запись в модуле записи при его удалении.

Ниже приведен пример входных данных JSON для обработки в примере кода:

:::code language="json" source="snippets/system-text-json-how-to/csharp/Grades.json":::

В результате получаются следующие структурированные выходные данные JSON:

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-utf8jsonwriter"></a>Использование Utf8JsonWriter

В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs" id="Serialize":::

## <a name="use-utf8jsonreader"></a>Использование Utf8JsonReader

В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs" id="Deserialize":::

В приведенном выше коде предполагается, что переменной `jsonUtf8` является массив байтов, который содержит допустимые данные JSON в кодировке UTF-8.

### <a name="filter-data-using-utf8jsonreader"></a>Фильтрация данных с помощью Utf8JsonReader

В следующем примере показано, как синхронно выполнить чтение файла и поиск значения.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs":::

Версию примера с асинхронными операциями см. в [проекте JSON с примерами для .NET](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs).

Предыдущий код:

* Предполагается, что JSON содержит массив объектов и каждый объект может содержать свойство name строкового типа.
* Подсчитывает объекты и значения свойств name, заканчивающиеся на University.
* Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8. Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>` с помощью следующего кода:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Если файл содержит метку порядка байтов (BOM) UTF-8, удалите ее перед передачей байтов в `Utf8JsonReader`, так как средство чтения ждет текст. В противном случае метка порядка байтов считается недопустимым кодом JSON, и средство чтения создает исключение.

Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода. Полученным итоговым сообщением будет 2 out of 4 have names that end with University (2 из 4 имеют имена, заканчивающиеся на University):

:::code language="json" source="snippets/system-text-json-how-to/csharp/Universities.json":::

### <a name="read-from-a-stream-using-utf8jsonreader"></a>Чтение из потока данных с помощью Utf8JsonReader

При чтении большого файла (размером гигабайт и более) вы, скорее всего, предпочтете не загружать весь файл в память сразу. В таких ситуациях можно использовать <xref:System.IO.FileStream>.

При использовании `Utf8JsonReader` для чтения из потока данных действуют следующие правила:

* Буфер, который накапливает часть данных в формате JSON, должен быть не меньше самого крупного из возможных маркеров JSON, чтобы средство чтения могло продвигаться вперед.
* Размер буфера должен быть не меньше самой большой последовательности пробелов в JSON.
* Средство чтения не запоминает прочитанные данные, пока не дойдет до следующего свойства <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> в структуре JSON. Таким образом, если в буфере еще остались байты, их нужно снова передать в средство чтения. Для определения количества оставшихся байтов можно использовать <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A>.

В примере кода ниже показано, как выполнять чтение из потока. Этот пример демонстрирует <xref:System.IO.MemoryStream>. Аналогичный код будет работать и с <xref:System.IO.FileStream>, за исключением случаев, когда в начале `FileStream` содержится метка порядка байтов UTF-8. В этом случае необходимо удалить эти три байта из буфера, прежде чем передавать оставшиеся байты в `Utf8JsonReader`. В противном случае средство чтения создаст исключение, поскольку метка порядка байтов не считается допустимой частью JSON.

Пример кода начинает работу с буфером в 4 КБ и удваивает размер буфера каждый раз, когда тот оказывается недостаточно велик для размещения полного маркера JSON, который потребуется средству чтения для дальнейшего перемещения по структуре данных JSON. Представленный в этом примере фрагмент JSON приводит к увеличению размера буфера только в том случае, если задан очень маленький начальный размер буфера, например 10 байт. Если указать для буфера начальное значение 10, то инструкции `Console.WriteLine` продемонстрируют причину и последствия увеличения размера буфера. При начальном размере буфера 4 КБ весь пример JSON целиком отображается в каждой `Console.WriteLine`, и размер буфера увеличивать не нужно.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs":::

В примере выше ограничение на увеличение размера буфера не установлено. Если размер маркера будет слишком большой, такой код может возвратить ошибку с исключением <xref:System.OutOfMemoryException>. Такое может произойти, если в JSON есть маркер размером около 1 ГБ, поскольку удвоение размера 1 ГБ приводит к переполнению буфера `int32`.

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Настройка кодировки символов](system-text-json-character-encoding.md)
* [Как написать настраиваемые преобразователи для сериализации JSON (маршалинг) в .NET](system-text-json-converters-how-to.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
