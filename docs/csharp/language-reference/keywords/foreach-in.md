---
description: foreach, in (справочник по C#)
title: Оператор foreach в C#
ms.date: 09/18/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: ea8a6f86595348a32b707caf9782f84147fefc87
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828894"
---
# <a name="foreach-in-c-reference"></a>foreach, in (справочник по C#)

Оператор `foreach` выполняет оператор или блок операторов для каждого элемента в экземпляре типа, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>, как показано в следующем примере.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

Оператор `foreach` не ограничен этими типами. Его можно использовать с экземпляром любого типа, который удовлетворяет следующим условиям:

- тип содержит открытый метод `GetEnumerator` без параметров со следующим типом возвращаемого значения: класс, структура или тип интерфейса. Начиная с C# 9.0 метод `GetEnumerator` может быть [методом расширения](../../programming-guide/classes-and-structs/extension-methods.md) типа.
- тип возвращаемого значения метода `GetEnumerator` должен содержать открытое свойство `Current` и открытый метод `MoveNext` без параметров с типом возвращаемого значения <xref:System.Boolean>.

В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Span%601?displayProperty=nameWithType>, который не реализует интерфейс:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

Начиная с версии C# 7.3, если свойство перечислителя `Current` возвращает [ссылочное возвращаемое значение](ref.md#reference-return-values) (`ref T`, где `T` — это тип элемента коллекции), вы можете объявить переменную итерации с модификатором `ref` или `ref readonly`, как показано в следующем примере.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

Начиная с C# 8.0, можно применять оператор `await foreach` для использования асинхронного потока данных, то есть типа коллекции, реализующего интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601>. Каждую итерацию цикла можно приостановить, пока будет осуществляться асинхронное извлечение следующего элемента. В следующем примере показано использование оператора `await foreach`.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

Элементы потока по умолчанию обрабатываются в захваченном контексте. Чтобы отключить захват контекста, используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Дополнительные сведения о контекстах синхронизации и захвате текущего контекста см. в статье [Использование асинхронного шаблона, основанного на задачах](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md). Дополнительные сведения об асинхронных потоках см. в разделе [Асинхронные потоки](../../whats-new/csharp-8.md#asynchronous-streams) статьи [Новые возможности в C# 8.0](../../whats-new/csharp-8.md).

В любой момент в блоке операторов `foreach` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md). Можно также выйти из цикла `foreach` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).

Если оператор `foreach` применяется к `null`, возникает исключение <xref:System.NullReferenceException>. Если исходная коллекция инструкции `foreach` пустая, тело цикла `foreach` не выполняется и пропускается.

## <a name="type-of-an-iteration-variable"></a>Тип переменной итерации

Можно использовать ключевое слово `var`, чтобы компилятор мог определить тип переменной итерации в операторе `foreach`, как показано в следующем коде:

```csharp
foreach (var item in collection) { }
```

Можно также явно указать тип переменной итерации, как показано в следующем коде:

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

В предыдущей форме тип `T` элемента коллекции должен быть неявно или явно преобразован в тип `V` переменной итерации. Если явное преобразование из `T` в `V` завершается ошибкой во время выполнения, оператор `foreach` выдает исключение <xref:System.InvalidCastException>. Например, если `T` является незапечатанным типом класса, `V` может быть любым типом интерфейса, даже тем, который `T` не реализует. Во время выполнения тип элемента коллекции может быть производным от `T` и фактически реализовать `V`. В противном случае возникает <xref:System.InvalidCastException>.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор foreach](~/_csharplang/spec/statements.md#the-foreach-statement) в документации [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).

Дополнительные сведения о функциях, добавленных в C# 8.0 и более поздние версии, см. в следующих заметках о функциях.

- [Асинхронные потоки (C# 8.0)](~/_csharplang/proposals/csharp-8.0/async-streams.md)
- [Поддержка расширения `GetEnumerator` для циклов `foreach` (C# 9.0)](~/_csharplang/proposals/csharp-9.0/extension-getenumerator.md)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Ключевые слова C#](index.md)
- [Использование оператора foreach с массивами](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [Оператор for](for.md)
