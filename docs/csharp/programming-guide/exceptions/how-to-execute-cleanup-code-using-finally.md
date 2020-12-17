---
title: Руководство по программированию на C#. Выполнение кода очистки с использованием блока finally
description: Сведения о выполнении кода очистки с использованием оператора finally. Операторы finally гарантируют, что все необходимые очистки объектов происходят немедленно.
ms.date: 12/09/2020
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: e9b5d3086488d3f7e3c0709317d6fafd15c439e8
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110186"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a>Руководство по программированию на C#. Выполнение кода очистки с использованием блока finally

Оператор `finally` позволяет гарантировать, что необходимая очистка объектов, как правило, объектов, занимающих внешние ресурсы, возникает немедленно, даже при создании исключения. Примером подобной очистки является вызов <xref:System.IO.Stream.Close%2A> для <xref:System.IO.FileStream> сразу после использования вместо ожидания сборки мусора, выполняемой для объекта средой CLR, следующим образом:

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="NoCleanup":::

## <a name="example"></a>Пример

Чтобы преобразовать предыдущий код в оператор `try-catch-finally`, код очистки отделяется от рабочего кода следующим образом:

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="WithCleanup":::

Так как исключение в блоке `try` может возникнуть в любой момент до вызова `OpenWrite()` или может произойти сбой самого вызова `OpenWrite()`, мы не можем гарантировать, что файл, который мы попытаемся закрыть, будет в это время открыт. Блок `finally` добавляет проверку того, что объект <xref:System.IO.FileStream> — не `null`, перед вызовом метода <xref:System.IO.Stream.Close%2A>. Без проверки `null` блок `finally` может вызывать собственное исключение <xref:System.NullReferenceException>, однако вызова исключений в блоках `finally` следует по возможности избегать.

Подключение к базе данных — еще один подходящий кандидат для заключения в блок `finally`. Так как количество разрешенных подключений к серверу базы данных иногда ограничено, закрывать подключения к базе данных рекомендуется как можно быстрее. Если перед закрытием подключения возникает исключение, рекомендуется использовать блок `finally`, а не ожидать сборки мусора.

## <a name="see-also"></a>См. также

- [Оператор using](../../language-reference/keywords/using-statement.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
