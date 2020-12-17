---
title: Руководство по программированию на C#. Обработка исключений
description: Сведения об обработке исключений. Изучите примеры операторов try-catch, try-finally и try-catch-finally.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: fabf1413ba498232e67f45460195fe96e25fab0a
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110199"
---
# <a name="exception-handling-c-programming-guide"></a>Обработка исключений (Руководство по программированию на C#)

Блок [try](../../language-reference/keywords/try-catch.md) используется программистами C# для разбиения на разделы кода, который может затрагиваться исключением. Связанные с ним блоки [catch](../../language-reference/keywords/try-catch.md) используются для обработки возможных исключений. Блок [finally](../../language-reference/keywords/try-finally.md) содержит код, выполняемый вне зависимости от того, вызывается ли исключение в блоке `try`, например для освобождения ресурсов, выделенных в блоке `try`. Блоку `try` требуется один или несколько связанных блоков `catch` или блок `finally` (либо и то, и другое).

В приведенных ниже примерах показаны операторы `try-catch`, `try-finally` и `try-catch-finally`.

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryFinallyStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchFinallyStructure":::

Блок `try` без блока `catch` или блока `finally` вызовет ошибку компилятора.

## <a name="catch-blocks"></a>Блоки catch

Блок `catch` может определять тип перехватываемого исключения. Спецификация типа называется *фильтром исключений*. Тип исключения должен быть производным от <xref:System.Exception>. Как правило, не следует задавать <xref:System.Exception> в качестве фильтра исключений, кроме случаев, когда известно, как обрабатывать все исключения, которые могут быть вызваны в блоке `try`, или когда оператор [throw](../../language-reference/keywords/throw.md) добавлен в конце блока `catch`.

Несколько блоков `catch` с различными классами исключений могут быть соединены в цепочку. Блоки `catch` проверяются сверху вниз в коде, однако для каждого вызванного исключения выполняется только один блок `catch`. Выполняется первый блок `catch`, в котором указан точный тип или базовый класс вызванного исключения. Если нет блока `catch`, в котором определен соответствующий класс исключений, выбирается блок `catch`, в котором нет выбранного типа, если таковой имеется в операторе. Важно, чтобы первыми были размещены блоки `catch` с самыми конкретными (т. е. самыми производными) типами исключений.

Исключения следует перехватывать при выполнении указанных ниже условий.

- Вы ясно понимаете возможные причины вызова исключения и можете выполнить восстановление, например, предложив пользователю ввести новое имя файла при перехвате объекта <xref:System.IO.FileNotFoundException>.
- Вы можете создать и вызвать новое, более конкретное исключение.
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="ThrowMoreSpecificException":::
- Требуется частично обработать исключение перед передачей его на дополнительную обработку. В следующем примере блок `catch` используется для добавления записи в журнал ошибок перед повторным вызовом исключения.
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="RethrowError":::

Вы также можете указывать *фильтры исключений*, чтобы добавить логическое выражение в предложение catch. Они указывают, что конкретное предложение catch соответствует только в том случае, если условие истинно. В следующем примере оба предложения catch используют один и тот же класс исключения, но для создания другого сообщения об ошибке проверяется дополнительное условие.

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="DemonstrateExceptionFilter":::

Фильтр исключений, который всегда возвращает `false`, можно использовать для проверки всех исключений, но не для их обработки. Обычно он используется для регистрации исключений:

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="ShowExceptionFilter":::

Метод `LogException` всегда возвращает `false`, и ни одно предложение `catch`, использующее этот фильтр, не является соответствующим. Предложение catch может быть общим с использованием <xref:System.Exception?displayProperty=nameWithType>, а последующие предложения могут обрабатывать более конкретные классы исключений.

## <a name="finally-blocks"></a>Блоки "Finally"

Блок `finally` позволяет удалить действия, выполненные в блоке `try`. При наличии блока `finally` он выполняется последним, после блока `try` и всех выполняемых блоков `catch`. Блок `finally` выполняется всегда, независимо от того, возникло ли исключение, или найден ли блок `catch`, соответствующий типу исключения.

Блок `finally` можно использовать для высвобождения ресурсов, например потоков данных, подключений к базам данных, графических дескрипторов, не ожидая финализации объектов сборщиком мусора во время выполнения. Дополнительные сведения см. в разделе [Оператор using](../../language-reference/keywords/using-statement.md).

В приведенном ниже примере с помощью блока `finally` закрывается файл, открытый в блоке `try`. Обратите внимание, что состояние дескриптора файла проверяется до закрытия файла. Если блок `try` не может открыть этот файл, то дескриптор файла сохраняет значение `null`, и блок `finally` не пытается закрыть его. И наоборот, если файл успешно открыт в блоке `try`, блок `finally` закрывает открытый файл.

:::code language="csharp" source="snippets/exceptions/Program.cs" id="CleanupIfNotNull":::

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделах [Исключения](~/_csharplang/spec/exceptions.md) и [Оператор try](~/_csharplang/spec/statements.md#the-try-statement) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../language-reference/index.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [Оператор using](../../language-reference/keywords/using-statement.md)
