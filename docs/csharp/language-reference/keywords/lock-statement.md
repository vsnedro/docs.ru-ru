---
title: Инструкция lock. Справочник по C#
description: Синхронизация доступа потоков к общему ресурсу с помощью оператора блокировки C#
ms.date: 04/02/2020
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2f2d42ae02a07a5e1b82cefd004f4d03b2a16dff
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635383"
---
# <a name="lock-statement-c-reference"></a>Инструкция lock. (Справочник по C#)

Оператор `lock` получает взаимоисключающую блокировку заданного объекта перед выполнением определенных операторов, а затем снимает блокировку. Во время блокировки поток, удерживающий блокировку, может снова поставить и снять блокировку. Любой другой поток не может получить блокировку и ожидает ее снятия.

Оператор `lock` имеет форму

```csharp
lock (x)
{
    // Your code...
}
```

Здесь `x` — это выражение [ссылочного типа](reference-types.md). Оно является точным эквивалентом

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

Так как в коде используется блок [try... finally](try-finally.md), блокировка освобождается, даже если возникает исключение в теле оператора `lock`.

Нельзя использовать [оператор await](../operators/await.md) в теле оператора `lock`.

## <a name="guidelines"></a>Рекомендации

При синхронизации доступа потоков к общему ресурсу блокируйте выделенный экземпляр объекта (например, `private readonly object balanceLock = new object();`) или другой экземпляр, который, скорее всего, не будет использоваться как объект блокировки другими частями кода. Не используйте один и тот же экземпляр объекта блокировки для разных общих ресурсов: это может привести к взаимоблокировке или состязанию при блокировке. В особенности избегайте использования следующих объектов в качестве объектов блокировки:

- `this`, так как он может использоваться вызывающими объектами как блокировка;
- экземпляров <xref:System.Type>, так как их может получать оператор [typeof](../operators/type-testing-and-cast.md#typeof-operator) или отражение;
- строковых экземпляров, включая строковые литералы, так как они могут быть [интернированы](/dotnet/api/system.string.intern#remarks).

Удерживайте блокировку в течение максимально короткого времени, чтобы сократить число конфликтов при блокировке.

## <a name="example"></a>Пример

В следующем примере определяется класс `Account`, который синхронизирует доступ к закрытому полю `balance` путем блокировки выделенного экземпляра `balanceLock`. Использование того же экземпляра для блокировки гарантирует, что поле `balance` не смогут одновременно обновить два потока, пытающиеся вызвать методы `Debit` или `Credit` одновременно.

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе об [инструкции lock](~/_csharplang/spec/statements.md#the-lock-statement) в документации [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Ключевые слова C#](index.md)
- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Обзор примитивов синхронизации](../../../standard/threading/overview-of-synchronization-primitives.md)
