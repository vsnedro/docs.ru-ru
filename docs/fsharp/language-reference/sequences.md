---
title: Последовательности
description: 'Узнайте, как использовать последовательности F # при наличии большой упорядоченной коллекции данных, но не обязательно должны использовать все элементы.'
ms.date: 08/13/2020
ms.openlocfilehash: c84e0aebcc79a595c0ae3b9075648fb629bdd65c
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559041"
---
# <a name="sequences"></a>Последовательности

*Последовательность* — это логический ряд элементов одного типа. Последовательности особенно полезны при наличии большой упорядоченной коллекции данных, но не обязательно должны использовать все элементы. Отдельные элементы последовательности вычисляются только по мере необходимости, поэтому последовательность может обеспечить лучшую производительность, чем список в ситуациях, когда не все элементы используются. Последовательности представлены `seq<'T>` типом, который является псевдонимом для <xref:System.Collections.Generic.IEnumerable%601> . Поэтому в качестве последовательности можно использовать любой тип .NET, реализующий <xref:System.Collections.Generic.IEnumerable%601> интерфейс. [Модуль Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) обеспечивает поддержку манипуляций с последовательностями.

## <a name="sequence-expressions"></a>Выражения последовательности

*Выражение последовательности* — это выражение, результатом которого является последовательность. Выражения последовательности могут принимать несколько форм. В самой простой форме указывается диапазон. Например, `seq { 1 .. 5 }` создает последовательность, содержащую пять элементов, включая конечные точки 1 и 5. Можно также указать шаг приращения (или уменьшение) между двумя двойными точками. Например, следующий код создает последовательность кратных 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Выражения последовательности состоят из выражений F #, создающих значения последовательности. Значения также можно формировать программно:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

В предыдущем примере используется `->` оператор, который позволяет указать выражение, значение которого станет частью последовательности. Можно использовать, только `->` если каждая часть кода, следующая за ней, возвращает значение.

Кроме того, можно указать `do` ключевое слово с необязательным `yield` следующим образом:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

Следующий код создает список пар координат и индексов в массиве, представляющем сетку. Обратите внимание, что `for` для первого выражения требуется `do` указать.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

`if`Выражение, используемое в последовательности, является фильтром. Например, чтобы создать последовательность только простых чисел, при условии, что имеется функция `isprime` типа `int -> bool` , создайте последовательность следующим образом.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Как упоминалось ранее, `do` требуется здесь, так как нет `else` ветви, которая перемещается с `if` . Если вы попытаетесь использовать `->` , вы получите сообщение об ошибке, сообщающее, что не все ветви возвращают значение.

## <a name="the-yield-keyword"></a>Ключевое слово `yield!`.

Иногда может потребоваться включить последовательность элементов в другую последовательность. Чтобы включить последовательность в другую последовательность, необходимо использовать `yield!` ключевое слово:

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

Другой способ подумать `yield!` заключается в том, что он выполняет сведение внутренней последовательности, а затем включает его в содержащую последовательность.

При `yield!` использовании в выражении все остальные одиночные значения должны использовать `yield` ключевое слово:

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

В предыдущем примере значение будет выдаваться `x` в дополнение ко всем значениям `1` для `x` каждого из них `x` .

## <a name="examples"></a>Примеры

В первом примере используется выражение последовательности, содержащее итерацию, фильтр и оператор yield для создания массива. Этот код выводит на консоль последовательность простых чисел от 1 до 100.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

В следующем примере создается таблица умножения, состоящая из кортежей из трех элементов, каждый из которых состоит из двух факторов и продукта:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

В следующем примере показано использование `yield!` для объединения отдельных последовательностей в одну последнюю последовательность. В этом случае последовательности для каждого поддерева в двоичном дереве объединяются в рекурсивную функцию для создания конечной последовательности.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>Использование последовательностей

Последовательности поддерживают многие из тех же функций, что и [списки](lists.md). Последовательности также поддерживают операции, такие как группирование и подсчет, с помощью функций создания ключа. Последовательности также поддерживают более разнообразные функции для извлечения подпоследовательностей.

Многие типы данных, такие как списки, массивы, наборы и карты, являются неявными последовательностями, так как они являются перечислимыми коллекциями. Функция, которая принимает последовательность в качестве аргумента, работает с любыми распространенными типами данных F # в дополнение к любому типу данных .NET, реализующему `System.Collections.Generic.IEnumerable<'T>` . Сравните это с функцией, которая принимает список в качестве аргумента, который может принимать только списки. Тип `seq<'T>` является аббревиатурой типа для `IEnumerable<'T>` . Это означает, что любой тип, реализующий универсальный объект `System.Collections.Generic.IEnumerable<'T>` , включающий массивы, списки, наборы и карты в F #, а также большинство типов коллекций .NET, совместим с `seq` типом и может использоваться везде, где ожидается последовательность.

## <a name="module-functions"></a>Функции модуля

[Модуль Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) в [пространстве имен FSharp. Collections](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections.html) содержит функции для работы с последовательностями. Эти функции также работают с списками, массивами, картами и наборами, так как все эти типы являются перечислимыми и поэтому могут рассматриваться как последовательности.

## <a name="creating-sequences"></a>Создание последовательностей

Последовательности можно создавать с помощью выражений последовательности, как описано выше, или с помощью определенных функций.

Можно создать пустую последовательность с помощью [Seq. Empty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#empty)или создать последовательность только одного указанного элемента с помощью [Seq. Singleton](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#singleton).

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

Для создания последовательности, для которой создаются элементы с помощью предоставляемой функции, можно использовать [Seq.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#init) . Вы также предоставляете размер последовательности. Эта функция аналогична [List.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#init), за исключением того, что элементы не создаются до выполнения итерации по последовательности. В следующем коде показано использование `Seq.init` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

Выходные данные:

```console
0 10 20 30 40
```

С помощью функции [Seq. офаррай](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofArray) и [seq. офлист&#60;&#62;](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofList)можно создавать последовательности из массивов и списков. Однако массивы и списки можно также преобразовать в последовательности с помощью оператора приведения. В следующем коде показаны оба метода.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

С помощью [Seq. Cast](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cast)можно создать последовательность из слабо типизированной коллекции, например, определенных в `System.Collections` . Такие слабо типизированные коллекции имеют тип элемента `System.Object` и перечисляются с помощью неуниверсального `System.Collections.Generic.IEnumerable&#96;1` типа. Следующий код иллюстрирует использование `Seq.cast` для преобразования `System.Collections.ArrayList` в последовательность.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

Можно определить бесконечные последовательности с помощью функции [Seq.iniтинфините](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#initInfinite) . Для такой последовательности необходимо предоставить функцию, которая создает каждый элемент из индекса элемента. Бесконечные последовательности возможны из-за отложенного вычисления. элементы создаются по мере необходимости путем вызова указанной функции. В следующем примере кода создается неограниченная последовательность чисел с плавающей запятой, в данном случае чередующийся ряд квадратов последовательных целых чисел.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq. unfold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#unfold) создает последовательность из вычислительной функции, которая принимает состояние и преобразует его для создания каждого последующего элемента последовательности. Состояние — это просто значение, используемое для расчета каждого элемента, и может изменяться при вычислении каждого элемента. Вторым аргументом для `Seq.unfold` является начальное значение, используемое для запуска последовательности. `Seq.unfold` использует тип параметра для состояния, что позволяет завершить последовательность, возвращая `None` значение. В следующем коде показаны два примера последовательностей: `seq1` и `fib` , которые создаются `unfold` операцией. Первая — `seq1` это просто последовательность с числами до 20. Второе, `fib` ,, использует `unfold` для расчета последовательности Фибоначчи. Поскольку каждый элемент последовательности Фибоначчи является суммой двух предыдущих чисел Фибоначчи, значение состояния является кортежем, состоящим из двух предыдущих чисел в последовательности. Начальное значение — это `(1,1)` первые два числа в последовательности.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

Вывод выглядит следующим образом.

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

Ниже приведен пример кода, в котором используются многие из описанных здесь функций модуля последовательности для создания и расчета значений бесконечных последовательностей. Выполнение кода может занять несколько минут.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>Поиск и поиск элементов

Функции поддержки последовательностей доступны в списках: [Seq. Exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), [Seq. exists2-](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), [Seq. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#find), [Seq. findIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#findIndex), [Seq. Pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pick), [Seq. tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFind)и [Seq. tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex). Версии этих функций, доступные для последовательностей, оценивают последовательность только до элемента, для которого выполняется поиск. Примеры см. в разделе [списки](lists.md).

## <a name="obtaining-subsequences"></a>Получение подпоследовательностей

[Seq. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#filter) и [Seq. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#choose) подобны соответствующим функциям, доступным для списков, за исключением того, что фильтрация и выбор не выполняются до оценки элементов последовательности.

[Seq. truncate](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#truncate) создает последовательность из другой последовательности, но ограничивает ее заданным числом элементов. [Seq. take](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#take) создает новую последовательность, содержащую только заданное число элементов из начала последовательности. Если в последовательности меньше элементов, чем указано для выполнения, `Seq.take` создает исключение `System.InvalidOperationException` . Разница между `Seq.take` и `Seq.truncate` заключается в том, что не `Seq.truncate` создает ошибку, если число элементов меньше указанного числа.

В следующем коде показано поведение и различия между `Seq.truncate` и `Seq.take` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

Выходные данные до возникновения ошибки выглядят следующим образом.

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

С помощью [Seq. TakeWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#takeWhile)можно указать функцию предиката (логическую функцию) и создать последовательность из другой последовательности, состоящие из элементов исходной последовательности, для которых предикат имеет значение `true` , но останавливаться перед первым элементом, для которого предикат возвращает `false` . [Seq. Skip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skip) возвращает последовательность, которая пропускает заданное число первых элементов другой последовательности и возвращает остальные элементы. [Seq. SkipWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skipWhile) возвращает последовательность, которая пропускает первые элементы другой последовательности, если предикат возвращает `true` , а затем возвращает оставшиеся элементы, начиная с первого элемента, для которого предикат возвращает `false` .

В следующем примере кода показано поведение и различия между, и `Seq.takeWhile` `Seq.skip` `Seq.skipWhile` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

Выходные данные выглядят следующим образом.

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Преобразование последовательностей

Функция [Seq. парная](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pairwise) создает новую последовательность, в которой последовательные элементы входной последовательности группируются по кортежам.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq. windowd](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#windowed) имеет следующий `Seq.pairwise` смысл, за исключением того, что вместо создания последовательности кортежей создается последовательность массивов, которая содержит копии смежных элементов ( *окна*) из последовательности. Вы указываете число соседних элементов в каждом массиве.

В следующем коде показано использование функции `Seq.windowed`. В этом случае число элементов в окне равно 3. В примере используется `printSeq` , который определен в предыдущем примере кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

Выходные данные выглядят следующим образом.

Начальная последовательность:

```console
1.0 1.5 2.0 1.5 1.0 1.5

Windows of length 3:
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|]

Moving average:
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>Операции с несколькими последовательностями

[Seq.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip) и [Seq.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip3) принимают две или три последовательности и создают последовательность кортежей. Эти функции подобны соответствующим функциям, доступным для [списков](lists.md). Нет соответствующей функциональности для разделения одной последовательности на две или более последовательностей. Если эта функция необходима для последовательности, преобразуйте последовательность в список и используйте [List. unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip).

## <a name="sorting-comparing-and-grouping"></a>Сортировка, сравнение и группирование

Функции сортировки, поддерживаемые для списков, также работают с последовательностями. Сюда входят [Seq. Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sort) и [Seq. sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sortBy). Эти функции выполняют итерацию всей последовательности.

Для сравнения двух последовательностей используется функция [Seq. компаревис](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#compareWith) . Функция сравнивает последовательные элементы в свою очередь и останавливается при обнаружении первой неравной пары. Все дополнительные элементы не участвуют в сравнении.

В следующем коде показано использование `Seq.compareWith`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

В предыдущем коде вычисляются и анализируются только первый элемент, а результат равен-1.

[Seq. каунтби](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#countBy) принимает функцию, которая создает значение, именуемое *ключом* для каждого элемента. Ключ создается для каждого элемента путем вызова этой функции для каждого элемента. `Seq.countBy` затем возвращает последовательность, содержащую значения ключа, и количество элементов, которые создали каждое значение ключа.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

Выходные данные выглядят следующим образом.

```console
(1, 34) (2, 33) (0, 33)
```

В предыдущих выходных данных показано, что имелось 34 элементов исходной последовательности, которые производили значение ключа 1, 33, которое вызвало ключ 2, и значение 33, полученное с помощью ключа 0.

Элементы последовательности можно сгруппировать, вызвав [Seq. GroupBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#groupBy). `Seq.groupBy` принимает последовательность и функцию, которая создает ключ из элемента. Функция выполняется для каждого элемента последовательности. `Seq.groupBy` Возвращает последовательность кортежей, где первый элемент каждого кортежа является ключом, а второй — последовательность элементов, которые создают этот ключ.

В следующем примере кода показано использование `Seq.groupBy` для секционирования последовательности чисел от 1 до 100 в три группы, имеющие уникальные значения ключа 0, 1 и 2.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

Выходные данные выглядят следующим образом.

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

Можно создать последовательность, которая устраняет повторяющиеся элементы, вызывая [Seq. DISTINCT](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinct). Или можно использовать [Seq. дистинктби](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinctBy), который принимает функцию создания ключа для каждого элемента. Результирующая последовательность содержит элементы исходной последовательности, имеющие уникальные ключи. последующие элементы, которые создают дубликат ключа для более раннего элемента, отбрасываются.

В следующем примере кода показано использование `Seq.distinct` . `Seq.distinct` демонстрируется путем создания последовательностей, представляющих двоичные числа, а затем показывается, что единственными отдельными элементами являются 0 и 1.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

Следующий код демонстрирует, `Seq.distinctBy` начиная с последовательности, содержащей отрицательные и положительные числа, и используя функцию абсолютного значения в качестве функции создания ключа. В результирующей последовательности отсутствуют все положительные числа, соответствующие отрицательным числам в последовательности, так как отрицательные числа отображаются ранее в последовательности и, следовательно, выбираются вместо положительных чисел, имеющих одинаковое абсолютное значение или ключ.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>Последовательностей только для чтения и кэширование

[Seq. ReadOnly](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#readonly) создает копию последовательности, доступную только для чтения. `Seq.readonly` может использоваться, если имеется коллекция для чтения и записи, например массив, и вы не хотите изменять исходную коллекцию. Эта функция может использоваться для сохранения инкапсуляции данных. В следующем примере кода создается тип, содержащий массив. Свойство предоставляет массив, но вместо возвращения массива он возвращает последовательность, созданную из массива с помощью `Seq.readonly` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq. Cache](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cache) создает сохраненную версию последовательности. Используйте, `Seq.cache` чтобы избежать повторного вычисления последовательности или при наличии нескольких потоков, использующих последовательность, но необходимо убедиться, что каждый элемент действует только один раз. При наличии последовательности, используемой несколькими потоками, у вас может быть один поток, который перечисляет и выполняет вычисление значений для исходной последовательности, а оставшиеся потоки могут использовать кэшированную последовательность.

## <a name="performing-computations-on-sequences"></a>Выполнение вычислений в последовательностях

Простые арифметические операции аналогичны спискам, например [Seq. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#average), [Seq. Sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sum), [Seq. averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#averageBy), [Seq. sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sumBy)и т. д.

Функции [Seq. fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#fold), [Seq. reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#reduce)и [Seq. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#scan) подобны соответствующим функциям, доступным для списков. Последовательности поддерживают подмножество всех вариантов этих функций, которые поддерживаются в списках. Дополнительные сведения и примеры см. в разделе [списки](lists.md).

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Типы языка F#](fsharp-types.md)
