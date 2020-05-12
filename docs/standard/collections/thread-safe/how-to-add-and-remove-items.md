---
title: Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из этой коллекции
ms.date: 05/04/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, concurrent dictionary
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
ms.openlocfilehash: 6e5204c5a71232ef9d1a050891e7fe6d92c375f2
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796123"
---
# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a>Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из этой коллекции

В этом примере показано, как добавлять, получать, обновлять и удалять элементы класса <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>. Этот класс коллекций является потокобезопасной реализацией. Рекомендуется использовать его каждый раз, когда множество потоков одновременно могут пытаться получить доступ к элементам.

<xref:System.Collections.Concurrent.ConcurrentDictionary%602> предоставляет несколько удобных способов, которые позволяют обойтись без первоначальной проверки существования ключа перед добавлением или удалением данных. В таблице ниже перечислены эти удобные методы и приводится описание их использования.

| Метод | Используется, если… |
|--|--|
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> | Необходимо добавить новое значение для заданного ключа, а также в том случае, если ключ уже существует и необходимо заменить его значение. |
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> | Необходимо получить существующее значение для заданного ключа, а также в том случае, если ключ не существует, и задать значение паре "ключ-значение". |
| <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A> | Необходимо добавить, получить, обновить или удалить пару "ключ-значение", а также в том случае, если ключ уже существует или попытка завершилась по какой-либо причине ошибкой и необходимо выполнить альтернативные действия. |

## <a name="example"></a>Пример

В приведенном ниже примере используются два экземпляра <xref:System.Threading.Tasks.Task> для одновременного добавления элементов в <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, после чего выводится все содержимое, чтобы показать, что элементы успешно добавлены. В примере также показано, как использовать методы <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> для добавления, обновления элементов и извлечения их из коллекции.

[!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
[!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]

Класс <xref:System.Collections.Concurrent.ConcurrentDictionary%602> предназначен для многопоточных сценариев. Необязательно использовать блокировки в коде для добавления или удаления элементов из коллекции. Однако всегда есть возможность для одного потока получить значение, а для другого потока немедленно обновить коллекцию, передавая тому же ключу новое значение.

Кроме того, несмотря на то, что все методы <xref:System.Collections.Concurrent.ConcurrentDictionary%602> потокобезопасны, не все методы атомарны, например <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>. Пользовательский делегат, передаваемый этим методам, вызывается вне внутренней блокировки словаря (это необходимо для того, чтобы предотвратить блокировку всех потоков неизвестным кодом). Поэтому может произойти следующая последовательность событий:

1. _Поток threadA_ вызывает <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, не находит элемент и создает элемент для добавления, вызывая делегат `valueFactory`.

1. _Поток threadB_ одновременно вызывает <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, вызывается его делегат `valueFactory`, и этот поток оказывается в состоянии внутренней блокировки раньше _потока threadA_, поэтому его новая пара "ключ — значение" добавляется в словарь.

1. Пользовательский делегат _потока threadA_ завершает работу, поток достигает блокировки, но видит, что теперь элемент уже существует.

1. _Поток threadA_ выполняет действие Get и возвращает данные, добавленные ранее _потоком threadB_.

Поэтому нет гарантии, что данные, возвращаемые методом <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, будут данными, созданными делегатом `valueFactory` потока. Аналогичная последовательность событий может иметь место при вызове метода <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.

## <a name="see-also"></a>См. также

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)
