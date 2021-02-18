---
title: Руководство по программированию на C#. Запись в текстовый файл
description: Узнайте, как выполнить запись данных в текстовый файл на C#. Изучите несколько примеров кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 02/11/2021
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.topic: how-to
ms.custom: contperf-fy21q3
ms.openlocfilehash: ecc3ba73161d4f4571bbc6ae0c9aaa3337586ef7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475621"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Руководство по программированию на C#. Запись в текстовый файл

В этой статье есть несколько примеров, демонстрирующих различные способы записи текста в файл. В первых двух примерах используются удобные статические методы класса <xref:System.IO.File?displayProperty=nameWithType> для записи каждого элемента любого объекта `IEnumerable<string>` и `string` в текстовый файл. В третьем примере показано, как добавить текст в файл, если необходимо обрабатывать отдельно каждую строку по мере ее записи в файл. В первых трех примерах происходит перезапись всего существующего содержимого файла. В последнем примере показано, как добавить текст в существующий файл.

 Все эти примеры записывают строковые литералы в файлы. Чтобы отформатировать записываемый в файл текст, воспользуйтесь методом <xref:System.String.Format%2A> или функцией [интерполяции строк](../../language-reference/tokens/interpolated.md) C#.

## <a name="write-a-collection-of-strings-to-a-file"></a>Запись коллекции строк в файл

:::code language="csharp" source="snippets/write-text/WriteAllLines.cs":::

Предыдущий пример исходного кода:

- Создает экземпляр массива строк с тремя значениями.
- Ожидает вызов <xref:System.IO.File.WriteAllLinesAsync%2A?displayProperty=nameWithType>, который:

  - Асинхронно создает имя файла *WriteLines.txt*. Если целевой файл уже существует, он будет перезаписан.
  - Записывает заданные строки в файл.
  - Закрывает файл, выполняет автоматическую очистку и удаление по мере необходимости.

## <a name="write-one-string-to-a-file"></a>Запись одной строки в файл

:::code language="csharp" source="snippets/write-text/WriteAllText.cs":::

Предыдущий пример исходного кода:

- Создает экземпляр строки с заданным назначенным строковым литералом.
- Ожидает вызов <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType>, который:

  - Асинхронно создает имя файла *WriteText.txt*. Если целевой файл уже существует, он будет перезаписан.
  - Записывает заданный текст в файл.
  - Закрывает файл, выполняет автоматическую очистку и удаление по мере необходимости.

## <a name="write-selected-strings-from-an-array-to-a-file"></a>Запись выбранных строк из массива в файл

:::code language="csharp" source="snippets/write-text/StreamWriterOne.cs":::

Предыдущий пример исходного кода:

- Создает экземпляр массива строк с тремя значениями.
- Создает экземпляр <xref:System.IO.StreamWriter> с путем к файлу *WriteLines2.txt* как [с помощью объявления](../../whats-new/csharp-8.md#using-declarations).
- Выполняет итерацию по всем строкам.
- Условно ожидает вызов <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType>, который записывает строку в файл, если строка не содержит `"Second"`.

## <a name="append-text-to-an-existing-file"></a>Добавление текста в существующий файл

:::code language="csharp" source="snippets/write-text/StreamWriterTwo.cs":::

Предыдущий пример исходного кода:

- Создает экземпляр массива строк с тремя значениями.
- Создает экземпляр <xref:System.IO.StreamWriter> с путем к файлу *WriteLines2.txt* как [с помощью объявления](../../whats-new/csharp-8.md#using-declarations), передавая `true` для добавления.
- Ожидает вызов <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType>, который записывает строку в файл как добавленную строку.

## <a name="exceptions"></a>Исключения

При следующих условиях возможно возникновение исключения:

- <xref:System.InvalidOperationException>: Файл существует и является файлом только для чтения.
- <xref:System.IO.PathTooLongException>: Имя пути имеет слишком большую длину.
- <xref:System.IO.IOException>: Диск может быть переполнен.

Существуют дополнительные условия, которые могут привести к возникновению исключений при работе с файловой системой, поэтому программировать следует с осторожностью.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Файловая система и реестр (руководство по программированию на C#)](./index.md)
- [Пример. Сохранение коллекции настраиваемых объектов в локальном хранилище](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
