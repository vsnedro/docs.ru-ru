---
description: Справочник по C#. Оператор try-finally
title: Справочник по C#. Оператор try-finally
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 03e5fa46cef6b30a0af15c113ec6b141a61bee47
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100639420"
---
# <a name="try-finally-c-reference"></a>try-finally (Справочник по C#)

С помощью блока `finally` можно выполнить очистку всех ресурсов, выделенных в блоке [try](try-catch.md), и запускать код даже при возникновении исключения в блоке `try`. Как правило, операторы блока `finally` выполняются, когда элемент управления покидает оператор `try`. Передача управления может возникать в результате нормального выполнения, выполнения операторов `break`, `continue`, `goto` или `return` или распространения исключения из оператора `try`.

Внутри обработанного исключения гарантируется выполнение связанного блока `finally`. Однако если исключение не обработано, то выполнение блока `finally` зависит от того, как запускается операция развертывания исключения. Это, в свою очередь, зависит от способа настройки компьютера. Единственные случаи, когда предложения `finally` не выполняются — немедленная остановка программы. Например, это может произойти при вызове исключения <xref:System.InvalidProgramException> из-за повреждения инструкций IL. В большинстве операционных систем при остановке и выгрузке процесса будет выполняться обоснованная очистка ресурсов.

Как правило, когда необработанное исключение приводит к завершению работы приложения, выполнение блока `finally` не имеет значения. Однако если в блоке `finally` есть операторы, которые необходимо запускать даже в такой ситуации, одним из решений является добавление блока `catch` в оператор `try`-`finally`. Кроме того, можно перехватить исключение, которое может создаваться в блоке `try` оператора `try`-`finally` выше в стеке вызовов. То есть можно перехватить исключение в методе, который вызывает метод, содержащий оператор `try`-`finally`, или в методе, который вызывает этот метод, или в любом методе в стеке вызовов. Если исключение не перехвачено, выполнение блока `finally` зависит от того, активирует ли операционная система операцию развертывания исключения.

## <a name="example"></a>Пример

В следующем примере недопустимый оператор преобразования вызывает исключение `System.InvalidCastException`. Исключение не обрабатывается.

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

В следующем примере исключение из метода `TryCast` перехватывается в методе выше в стеке вызовов.

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

Дополнительные сведения о `finally` см. в разделе [try-catch-finally](try-catch-finally.md).

C# также содержит [оператор using](using-statement.md), который предоставляет аналогичную функциональность для объектов <xref:System.IDisposable> в удобном синтаксисе.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор try](~/_csharplang/spec/statements.md#the-try-statement) в документации [Спецификация C# 6.0](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Операторы try, throw и catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [try-catch](try-catch.md)
- [Практическое руководство. Явное создание исключений](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
