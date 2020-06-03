---
title: Использование объектов, реализующих IDisposable
ms.date: 05/13/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: 87eefe2bd347ba1564b2f06d49bbee3b85efdb97
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287601"
---
# <a name="using-objects-that-implement-idisposable"></a>Использование объектов, реализующих IDisposable

Сборщик мусора среды CLR освобождает память, используемую управляемыми объектами. Но типы, которые используют неуправляемые ресурсы, реализуют интерфейс <xref:System.IDisposable>, который позволяет освободить ресурсы, которые требуются этим неуправляемым ресурсам. По окончании использования объекта, который реализует интерфейс <xref:System.IDisposable>, необходимо вызвать реализацию объекта <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. Это можно сделать одним из двух способов.

- С помощью оператора `using` (C#) или `Using` (Visual Basic).
- Путем реализации блока `try/finally` и вызова <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> в `finally`.

## <a name="the-using-statement"></a>Оператор using

[Оператор `using`](../../csharp/language-reference/keywords/using-statement.md) (C#) и [оператор `Using`](../../visual-basic/language-reference/statements/using-statement.md) (Visual Basic) упрощают написание кода для очистки объекта. Оператор `using` получает один или больше ресурсов, выполняет заданные операторы, после чего автоматически освобождает объект. Однако оператор `using` полезен только для объектов в области действия метода, в котором они созданы.

В следующем примере для создания и освобождения объекта `using` используется оператор <xref:System.IO.StreamReader?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]

Хотя класс <xref:System.IO.StreamReader> реализует интерфейс <xref:System.IDisposable>, который указывает, что используется неуправляемый ресурс, пример явно не вызывает метод <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>. Когда компилятор C# или Visual Basic встречает оператор `using`, он создает промежуточный язык, эквивалентный следующему коду, который явно содержит блок `try/finally`.

[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]

Оператор `using` в C# позволяет присоединять несколько ресурсов в одном операторе, что эквивалентно использованию вложенных инструкций `using`. В следующем примере создается два объекта <xref:System.IO.StreamReader> для чтения содержимого двух разных файлов.

[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a>Блок try/finally

Вместо размещения блока `try/finally` в операторе `using` можно реализовать блок `try/finally` напрямую. Это может отражать ваш стиль программирования или же осуществляться по одной из следующих причин:

- Чтобы включить блок `catch` для обработки исключений, вызванных в блоке `try`. В противном случае любые исключения, вызванные в операторе `using`, не обрабатываются.

- Чтобы создать экземпляр объекта, реализующего интерфейс <xref:System.IDisposable>, область действия которого не является локальной для блока, в котором он объявлен.

Следующий пример похож на предыдущий с тем отличием, что в нем используется блок `try/catch/finally`для создания, использования и удаления экземпляра объекта <xref:System.IO.StreamReader>, а также для обработки исключений, создаваемых конструктором <xref:System.IO.StreamReader> и его методом <xref:System.IO.StreamReader.ReadToEnd%2A>. Перед вызовом метода <xref:System.IDisposable.Dispose%2A> код в блоке `finally` проверяет, что объект, реализующий <xref:System.IDisposable>, не является `null`. Если этого сделать не удастся, это может привести к исключению <xref:System.NullReferenceException> во время выполнения.

[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]

Вы можете применить этот базовый шаблон, если есть желание или необходимость реализовать блок `try/finally` на языке программирования, который не поддерживает оператор `using`, но допускает прямые вызовы метода <xref:System.IDisposable.Dispose%2A>.

## <a name="idisposable-instance-members"></a>Члены экземпляра IDisposable

Если класс содержит реализацию <xref:System.IDisposable> в качестве члена экземпляра (поля или свойства), класс также должен реализовывать <xref:System.IDisposable>. См. сведения о [реализации каскадного удаления](implementing-dispose.md#cascade-dispose-calls).

## <a name="see-also"></a>См. также

- [Очистка неуправляемых ресурсов](unmanaged.md)
- [Оператор using (Справочник по C#)](../../csharp/language-reference/keywords/using-statement.md)
- [Оператор Using (Visual Basic)](../../visual-basic/language-reference/statements/using-statement.md)
