---
description: Справочник по C#. Оператор using
title: Справочник по C#. Оператор using
ms.date: 05/29/2020
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: c7f1fc4b7e911bdec3bd38ae88aa39b7f1795300
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141937"
---
# <a name="using-statement-c-reference"></a>Оператор using (справочник по C#)

Предоставляет удобный синтаксис, обеспечивающий правильное использование объектов <xref:System.IDisposable>. Начиная с C# 8.0 инструкция `using` гарантирует правильное использование объектов <xref:System.IAsyncDisposable>.

## <a name="example"></a>Пример

В следующем примере показано использование оператора `using`.

:::code language="csharp" source="snippets/usings.cs" id="SnippetFirstExample":::

Начиная с версии C# 8.0, можно использовать следующий альтернативный синтаксис для оператора `using` без использования фигурных скобок:

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernUsing":::

## <a name="remarks"></a>Примечания

<xref:System.IO.File> и <xref:System.Drawing.Font> представляют собой примеры управляемых типов, которые обращаются к неуправляемым ресурсам (в данном случае это обработчики файлов и контексты устройств). Существуют и многие другие виды неуправляемых ресурсов и типов библиотек классов, которые их инкапсулируют. Все эти типы должны реализовывать интерфейс <xref:System.IDisposable> или интерфейс <xref:System.IAsyncDisposable>.

Когда время существования объекта `IDisposable` ограничено одним методом, необходимо объявить его и создать его экземпляр в операторе `using`. Оператор `using` правильно вызывает метод <xref:System.IDisposable.Dispose%2A> для объектов, а также (если он используется, как показано выше) становится причиной выхода объекта из области действия, как только вызывается метод <xref:System.IDisposable.Dispose%2A>. В блоке `using` объект доступен только для чтения, и изменить или переназначить его невозможно. Если объект реализует `IAsyncDisposable` вместо `IDisposable`, то инструкция `using` вызывает <xref:System.IAsyncDisposable.DisposeAsync%2A> и `awaits`, возвращенный <xref:System.Threading.Tasks.ValueTask>. Дополнительные сведения о <xref:System.IAsyncDisposable> см. в статье [Реализация метода DisposeAsync](../../../standard/garbage-collection/implementing-disposeasync.md).

Использование инструкции `using` обеспечивает вызов <xref:System.IDisposable.Dispose%2A> (или <xref:System.IAsyncDisposable.DisposeAsync%2A>), даже если в блоке `using` возникает исключение. Тот же результат можно получить, поместив объект в блок `try`, а затем вызвав <xref:System.IDisposable.Dispose%2A> (или <xref:System.IAsyncDisposable.DisposeAsync%2A>) в блоке `finally`; фактически компилятор переводит инструкцию `using` именно так. Во время компиляции представленный выше код разворачивается в следующий (обратите внимание на дополнительные фигурные скобки, создающие ограниченную область действия для объекта):

:::code language="csharp" source="snippets/usings.cs" id="SnippetTryFinallyExample":::

Новый синтаксис инструкции `using` преобразуется в похожий код. Блок `try` открывается там, где объявлена переменная. Блок `finally` добавляется в конец охватывающего блока, как правило, в конце метода.

Дополнительные сведения об инструкции `try`-`finally` см. в описании [try-finally](try-finally.md).

В одной инструкции `using` можно объявить сразу несколько экземпляров типа, как показано в следующем примере. Обратите внимание, что невозможно использовать неявно типизированные переменные (`var`) при объявлении нескольких переменных в одной инструкции:

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareMultipleVariables":::

Несколько объявлений одного типа можно объединить с помощью нового синтаксиса, представленного в C# 8, как показано в следующем примере:

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernMultipleVariables":::

Вы можете создать экземпляр объекта ресурсов, а затем передать переменную в инструкцию `using`, однако делать это не рекомендуется. В этом случае объект остается в области действия и после того, как блок `using` теряет контроль, хотя доступа к неуправляемым ресурсам у него, скорее всего, не будет. Иными словами, он уже не полностью инициализируется. При попытке использовать объект за пределами блока `using` может возникнуть исключение. По этой причине лучше создать экземпляр объекта в инструкции `using` и ограничить область действия блоком `using`.

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareBeforeUsing":::

Дополнительные сведения об утилизации объектов `IDisposable` см. в разделе [Использование объектов, реализующих IDisposable](../../../standard/garbage-collection/using-objects.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор using](~/_csharplang/spec/statements.md#the-using-statement) в статье [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Директива using](using-directive.md)
- [Сборка мусора](../../../standard/garbage-collection/index.md)
- [Использование объектов, реализующих IDisposable](../../../standard/garbage-collection/using-objects.md)
- [Интерфейс IDisposable](xref:System.IDisposable)
- [Инструкция using в C# 8.0](~/_csharplang/proposals/csharp-8.0/using.md)
