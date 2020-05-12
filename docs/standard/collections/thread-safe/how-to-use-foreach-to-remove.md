---
title: Использование оператора foreach для удаления элементов из коллекции BlockingCollection
ms.date: 05/04/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collection
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
ms.openlocfilehash: 1255fcda89396ea8ff9abf6cf111e6dd9ea5a87d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82861009"
---
# <a name="use-foreach-to-remove-items-in-a-blockingcollection"></a>Использование оператора foreach для удаления элементов из коллекции BlockingCollection

Помимо извлечения элементов из коллекции <xref:System.Collections.Concurrent.BlockingCollection%601> с помощью методов <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, можно использовать цикл [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ([For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) в Visual Basic) с <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> для удаления элементов до тех пор, пока добавление не будет завершено и коллекция не станет пустой. Это называется *изменяющим перечислением* или *поглощающим перечислением*, поскольку, в отличие от типичного цикла `foreach` (`For Each`), этот перечислитель изменяет исходную коллекцию путем удаления элементов.

## <a name="example"></a>Пример

В приведенном ниже примере показано, как удалить все элементы в классе <xref:System.Collections.Concurrent.BlockingCollection%601>, используя цикл `foreach` (`For Each`).

[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
[!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]

Этот пример использует цикл `foreach` совместно с методом <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> в потоке-потребителе, что приводит к удалению каждого элемента из коллекции, как только он перечислен. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> ограничивает максимальное количество элементов, находящихся в коллекции в любой момент времени. Выполнение перечисления коллекции подобным образом блокирует поток-потребитель, если доступные элементы отсутствуют или коллекция является пустой. В этом примере блокировка не имеет значения, так как поток-производитель добавляет элементы быстрее, чем их может использовать потребитель.

<xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> возвращает `IEnumerable<T>`, поэтому невозможно гарантировать перечисление в том же порядке. Однако в качестве базового типа коллекции внутренним образом используется <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, который будет выводить объекты из очереди по принципу "первым поступил — первым обслужен" (FIFO). Если выполняются одновременные вызовы <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType>, они будут конкурировать. Один использованный элемент (выведенный из очереди) в одном перечислении не может присутствовать в другом.

Для перечисления коллекции без ее изменения просто используйте оператор `foreach` (`For Each`) без использования метода <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>. Тем не менее важно понимать, что такой тип перечисления представляет снимок коллекции в конкретный момент времени. Если другие потоки добавят или удалят элементы параллельно с выполнением цикла, цикл может не отобразить фактическое состояние коллекции.

## <a name="see-also"></a>См. также

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Параллельное программирование](../../../../docs/standard/parallel-programming/index.md)
