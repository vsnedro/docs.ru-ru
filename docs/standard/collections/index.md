---
title: Коллекции и структуры данных
description: Узнайте, как использовать коллекции и структуры данных в .NET. Используйте универсальные и неуниверсальные коллекции в потокобезопасных операциях.
ms.date: 04/30/2020
helpviewer_keywords:
- grouping data in collections
- objects [.NET], grouping in collections
- Array class, grouping data in collections
- threading [.NET], safety
- Collections classes
- collections [.NET]
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
ms.openlocfilehash: 7400d460c4d1ebf5c02d8313f33a5a63de1734d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733520"
---
# <a name="collections-and-data-structures"></a>Коллекции и структуры данных

Связанные данные могут обрабатываться более эффективно, если они объединены в коллекцию. Для добавления, удаления и изменения отдельных элементов или диапазона элементов коллекции можно использовать класс <xref:System.Array?displayProperty=nameWithType> или классы в пространствах имен <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent> и <xref:System.Collections.Immutable>.

Существует два основных типа коллекций — универсальные и неуниверсальные коллекции. Универсальные коллекции являются строго типизированными во время компиляции. Таким образом, универсальные коллекции обычно обеспечивают более высокую производительность. Универсальные коллекции принимают параметр типа во время создания и не требуют приведение в тип <xref:System.Object> и из него при добавлении или удалении элементов.  Кроме того, большая часть универсальных коллекций поддерживается в приложениях Microsoft Store. Неуниверсальные коллекции хранят такие элементы, как <xref:System.Object>, требуют приведения. Большая их часть не поддерживается для разработки приложений Microsoft Store. Однако неуниверсальные коллекции можно наблюдать в старом коде.

Начиная с .NET Framework 4, коллекции пространства имен <xref:System.Collections.Concurrent> предоставляют эффективные потокобезопасные операции для доступа к элементам коллекции из нескольких потоков. Неизменяемые классы коллекций в пространстве имен <xref:System.Collections.Immutable> ([пакет NuGet](https://www.nuget.org/packages/System.Collections.Immutable)) являются потокобезопасными, так как операции выполняются с копией исходной коллекции, а исходная коллекция неизменяемая.

<a name="BKMK_Commoncollectionfeatures"></a>

## <a name="common-collection-features"></a>Общие возможности коллекций

Все коллекции предоставляют методы для добавления, удаления или поиска элементов в коллекции. Кроме того, все коллекции прямо или косвенно реализуют интерфейс <xref:System.Collections.ICollection> или интерфейс <xref:System.Collections.Generic.ICollection%601> с совместным использованием следующих функций.

- **Возможность перечисления коллекции**

    Чтобы обеспечить итерацию по коллекции, коллекции .NET реализуют <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Перечислитель может рассматриваться как перемещаемый указатель на любой элемент в коллекции. Оператор [foreach, in](../../csharp/language-reference/keywords/foreach-in.md) и [For Each...Next Statement](../../visual-basic/language-reference/statements/for-each-next-statement.md) использует итератор, предоставляемый методом <xref:System.Collections.IEnumerable.GetEnumerator%2A>, и скрывает сложность работы с итератором. Кроме того, любая коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>, считается *запрашиваемым типом*, и к ней можно создавать запросы LINQ. Запросы LINQ предоставляют общий шаблон для доступа к данным. Обычно они являются более четкими и удобочитаемыми, чем стандартные циклы `foreach`, и предлагают возможности фильтрации, упорядочения и группировки. LINQ запросы также могут повысить производительность. Дополнительные сведения см. в разделах [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md), [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), [Введение в запросы LINQ (C#)](../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) и [Базовые операции с запросами (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).

- **Возможность копирования содержимого коллекции в массив**

    Все коллекции могут быть скопированы в массив с помощью метода **CopyTo**. Однако порядок элементов в новом массиве зависит от того, в какой последовательности их возвращает перечислитель. Результирующий массив всегда является одномерным массивом с нижней границей, равной нулю.

Кроме того, во многих классах коллекций реализованы следующие возможности.

- **Свойства "Емкость и количество элементов"**

    Емкость коллекции — это число элементов, которое она может содержать. Количество элементов коллекции — это число элементов, которое она реально содержит. В некоторых коллекциях емкость или количество элементов скрыты.

    Большинство коллекции автоматически увеличивают емкость, если количество элементов достигает предела. Происходит перераспределение памяти, и элементы копируются из старой коллекции в новую. Это уменьшает объем кода, необходимого для использования коллекции. Однако производительность при работе с такой коллекцией может ухудшиться. Например, если <xref:System.Collections.Generic.List%601.Count%2A> меньше <xref:System.Collections.Generic.List%601.Capacity%2A>, для <xref:System.Collections.Generic.List%601> добавление элемента является операцией O(1). Если емкость нужно увеличить для размещения нового элемента, добавление элемента становится операцией O(`n`), где `n` — это <xref:System.Collections.Generic.List%601.Count%2A>. Наилучший способ избежать потерь производительности, вызванных множественными перераспределениями, — это установить начальную вместимость, равную предполагаемому размеру коллекции.

    <xref:System.Collections.BitArray> является особым случаем; его емкость совпадает с его длиной, которая совпадает с количеством элементов.

- **Согласованная нижняя граница**

    Нижняя граница коллекции — это индекс ее первого элемента. Все индексированные коллекции в пространствах имен <xref:System.Collections> имеют нижнюю границу, равную нулю. Класс <xref:System.Array> по умолчанию имеет нижнюю границу, равную нулю, но при создании экземпляра класса **Array** с помощью <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> может быть задана другая нижняя граница.

- **Синхронизация для доступа из нескольких потоков** (только классы <xref:System.Collections>).

    Для типов неуниверсальных коллекций в пространстве имен <xref:System.Collections> синхронизация обеспечивает определенную степень потокобезопасности. Обычно для выполнения синхронизации используются члены <xref:System.Collections.ICollection.SyncRoot%2A> и <xref:System.Collections.ICollection.IsSynchronized%2A>. Эти коллекции не являются потокобезопасными по умолчанию. Если требуется масштабируемый и эффективный многопотоковый доступ к коллекции, используйте один из классов в пространстве имен <xref:System.Collections.Concurrent> или рассмотрите возможность использования неизменяемой коллекции. Дополнительные сведения см. в разделе [Потокобезопасные коллекции](thread-safe/index.md).

<a name="BKMK_Choosingacollection"></a>

## <a name="choose-a-collection"></a>Выбор коллекции

Как правило, следует использовать универсальные коллекции. В следующей таблице описаны некоторые основные сценарии использования коллекций и классы коллекций, которые можно использовать для этих сценариев. Если вы не работали с универсальными коллекциями, сведения в этой таблице помогут выбрать универсальную коллекцию, лучше всего подходящую для решения ваших задач.

|Действие|Возможности универсальной коллекции|Возможности неуниверсальной коллекции|Возможности потокобезопасной или неизменяемой коллекции|
|-|-|-|-|
|Хранение элементов в виде пар "ключ-значение" для быстрого поиска по ключу|<xref:System.Collections.Generic.Dictionary%602>|<xref:System.Collections.Hashtable><br /><br /> (Коллекция пар "ключ-значение", которые упорядочены по хэш-коду ключа.)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602><br /><br /> <xref:System.Collections.Immutable.ImmutableDictionary%602>|
|Доступ к элементам по индексу|<xref:System.Collections.Generic.List%601>|<xref:System.Array><br /><br /> <xref:System.Collections.ArrayList>|<xref:System.Collections.Immutable.ImmutableList%601><br /><br /> <xref:System.Collections.Immutable.ImmutableArray>|
|Использование элементов по принципу FIFO|<xref:System.Collections.Generic.Queue%601>|<xref:System.Collections.Queue>|<xref:System.Collections.Concurrent.ConcurrentQueue%601><br /><br /> <xref:System.Collections.Immutable.ImmutableQueue%601>|
|Использование данных по принципу LIFO|<xref:System.Collections.Generic.Stack%601>|<xref:System.Collections.Stack>|<xref:System.Collections.Concurrent.ConcurrentStack%601><br /><br /> <xref:System.Collections.Immutable.ImmutableStack%601>|
|Последовательный доступ к элементам|<xref:System.Collections.Generic.LinkedList%601>|Рекомендации отсутствуют|Рекомендации отсутствуют|
|Получение уведомлений при удалении элементов из коллекции или добавлении элементов в коллекцию. (реализует <xref:System.ComponentModel.INotifyPropertyChanged> и <xref:System.Collections.Specialized.INotifyCollectionChanged>)|<xref:System.Collections.ObjectModel.ObservableCollection%601>|Рекомендации отсутствуют|Рекомендации отсутствуют|
|Отсортированная коллекция|<xref:System.Collections.Generic.SortedList%602>|<xref:System.Collections.SortedList>|<xref:System.Collections.Immutable.ImmutableSortedDictionary%602><br /><br /> <xref:System.Collections.Immutable.ImmutableSortedSet%601>|
|Набор для математических функций|<xref:System.Collections.Generic.HashSet%601><br /><br /> <xref:System.Collections.Generic.SortedSet%601>|Рекомендации отсутствуют|<xref:System.Collections.Immutable.ImmutableHashSet%601><br /><br /> <xref:System.Collections.Immutable.ImmutableSortedSet%601>|

### <a name="algorithmic-complexity-of-collections"></a>Алгоритмическая сложность коллекций

При выборе [класса коллекции](selecting-a-collection-class.md) нужно учитывать возможное влияние на производительность. В следующей таблице сравнивается алгоритмическая сложность разных изменяемых типов коллекций и их соответствующих неизменяемых аналогов. Как правило, последние являются менее производительными, но их неизменяемость часто является преимуществом.

| Изменяемый                   | Амортизационный анализ  | Худший случай                | Неизменяемые                          | Сложность |
|---------------------------|------------|---------------------------|------------------------------------|------------|
| `Stack<T>.Push`           | O(1)       | O(`n`)                    | `ImmutableStack<T>.Push`           | O(1)       |
| `Queue<T>.Enqueue`        | O(1)       | O(`n`)                    | `ImmutableQueue<T>.Enqueue`        | O(1)       |
| `List<T>.Add`             | O(1)       | O(`n`)                    | `ImmutableList<T>.Add`             | O(log `n`) |
| `List<T>.Item[Int32]`     | O(1)       | O(1)                      | `ImmutableList<T>.Item[Int32]`     | O(log `n`) |
| `List<T>.Enumerator`      | O(`n`)     | O(`n`)                    | `ImmutableList<T>.Enumerator`      | O(`n`)     |
| `HashSet<T>.Add`, поиск  | O(1)       | O(`n`)                    | `ImmutableHashSet<T>.Add`          | O(log `n`) |
| `SortedSet<T>.Add`        | O(log `n`) | O(`n`)                    | `ImmutableSortedSet<T>.Add`        | O(log `n`) |
| `Dictionary<T>.Add`       | O(1)       | O(`n`)                    | `ImmutableDictionary<T>.Add`       | O(log `n`) |
| `Dictionary<T>`, поиск    | O(1)       | O(1) — или строго O(`n`) | `ImmutableDictionary<T>`, поиск    | O(log `n`) |
| `SortedDictionary<T>.Add` | O(log `n`) | O(`n` log `n`)            | `ImmutableSortedDictionary<T>.Add` | O(log `n`) |

`List<T>` можно эффективно перечислить с помощью цикла `for` или `foreach`. Но в случае с `ImmutableList<T>` использовать цикл `for` неэффективно, так как время для индексатора составляет O(log `n`). Перечисление `ImmutableList<T>` с помощью цикла `foreach` является эффективным, так как `ImmutableList<T>` использует двоичное дерево для хранения своих данных вместо простого массива, который использует `List<T>`. Массив можно быстро проиндексировать, тогда как двоичное дерево обрабатывается до тех пор, пока не будет найден узел с нужным индексом.

Кроме того, `SortedSet<T>` имеет ту же сложность, что и `ImmutableSortedSet<T>`. Это обусловлено тем, что в обоих случаях используются двоичные деревья. Существенная разница заключается в том, что `ImmutableSortedSet<T>` использует неизменяемое двоичное дерево. Так как `ImmutableSortedSet<T>` также предлагает класс <xref:System.Collections.Immutable.ImmutableSortedSet%601.Builder?displayProperty=nameWithType>, который допускает изменения, обеспечивается как неизменяемость, так и производительность.

<a name="BKMK_RelatedTopics"></a>

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Выбор класса коллекции](selecting-a-collection-class.md)|Описывает различные коллекций и содержит сведения по выбору коллекции, соответствующей сценарию пользователя.|
|[Часто используемые типы коллекций](commonly-used-collection-types.md)|Описывает часто используемые типы универсальных и неуниверсальных коллекций, таких как <xref:System.Array?displayProperty=nameWithType>, <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> и <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.|
|[Когда следует использовать универсальные коллекции](when-to-use-generic-collections.md)|Рассматривает использование типов универсальных коллекций.|
|[Сравнение и сортировка в коллекциях](comparisons-and-sorts-within-collections.md)|Описывает использование проверок равенства и сортировки в коллекциях.|
|[Отсортированные типы коллекций](sorted-collection-types.md)|Описывает производительность и характеристики отсортированных коллекций.|
|[Типы коллекций Hashtable и Dictionary](hashtable-and-dictionary-collection-types.md)|Описывает возможности универсальных и неуниверсальных типов словарей на основе хэша.|
|[Потокобезопасные коллекции](thread-safe/index.md)|Описывает типы коллекций, такие как <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> и <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>, поддерживающие безопасный и эффективный одновременный доступ из нескольких потоков.|
|System.Collections.Immutable|Приводятся вводные сведения о неизменяемых коллекциях и ссылки на типы коллекций.|

<a name="BKMK_Reference"></a>

## <a name="reference"></a>Справочник

<xref:System.Array?displayProperty=nameWithType>
<xref:System.Collections?displayProperty=nameWithType>
<xref:System.Collections.Concurrent?displayProperty=nameWithType>
<xref:System.Collections.Generic?displayProperty=nameWithType>
<xref:System.Collections.Specialized?displayProperty=nameWithType>
<xref:System.Linq?displayProperty=nameWithType>
<xref:System.Collections.Immutable>
