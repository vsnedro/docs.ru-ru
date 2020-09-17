---
title: Списки
description: 'Сведения о списках F #, упорядоченной, неизменяемой последовательности элементов одного и того же типа.'
ms.date: 08/13/2020
ms.openlocfilehash: 567731eb57b77d60d3dd847630d5676e8d047d09
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720352"
---
# <a name="lists"></a>Списки

В языке F# список — это упорядоченная, неизменная серия элементов одного типа. Для выполнения основных операций со списками используйте функции в [модуле List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).

## <a name="creating-and-initializing-lists"></a>Создание и инициализация списков

Список можно определить путем прямого перечисления элементов, разделенных точкой с запятой и заключенных в квадратные скобки, как показано в следующей строке кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

Вместо точки с запятой для разделения элементов можно также использовать разрыв строки. Такой синтаксис позволяет получить более удобный для чтения код, если список содержит длинные выражения инициализации или к каждому элементу необходимо написать комментарий.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

Обычно все элементы в списке должны быть одного типа. Исключением является список, в котором элементы основного типа могут иметь элементы производных типов. Следующий вариант считается приемлемым, так как типы `Button` и `CheckBox` являются производными от типа `Control`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

Определить элементы списка можно также с помощью диапазона, который будет ограничен целыми числами, разделенными оператором (`..`), как показано в следующем коде.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

Пустой список определяется парой квадратных скобок, между которыми ничего не указано.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

Также список можно создать с помощью выражения последовательности. Дополнительные сведения см. в разделе [выражения последовательностей](sequences.md#sequence-expressions) . Например, в следующем коде создается список квадратов целочисленных значений от 1 до 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a>Операторы для работы со списками

Оператор `::` позволяет добавлять элементы в список. Если список `list1` включает `[2; 3; 4]`, то следующий код создает список `list2` как `[100; 2; 3; 4]`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

Оператор `@` позволяет объединять списки совместимых типов, как показано в следующем коде. Если список `list1` включает `[2; 3; 4]`, список `list2` — `[100; 2; 3; 4]`, то следующий код создает список `list3` как `[2; 3; 4; 100; 2; 3; 4]`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

Функции для выполнения операций с списками доступны в [модуле List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).

Поскольку списки в языке F# являются неизменными, то операции изменения не изменяют существующие списки, а создают новые.

Списки в F # реализуются как однонаправленные списки. Это означает, что операции, обращающиеся только к заголовку списка, являются O (1), а доступ к элементу — O (*n*).

## <a name="properties"></a>Свойства

Тип списка поддерживает следующие свойства.

|Свойство|Type|Описание|
|--------|----|-----------|
|[Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|Первый элемент|
|[Пустой](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|Статическое свойство, которое возвращает пустой список соответствующего типа.|
|[IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|`true` значение, если список не содержит элементов.|
|[Элемент](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|Элемент с указанным индексом (начинается с нуля).|
|[Длина](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|Число элементов.|
|[Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|Список без первого элемента|

Ниже приведены некоторые примеры использования данных свойств.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a>Использование списков

Программирование с использованием списков позволяет выполнять сложные операции с небольшим количеством кода. В данном разделе описываются операции со списками, важные для функционального программирования.

### <a name="recursion-with-lists"></a>Рекурсия со списками

Списки однозначно подходят для техник рекурсивного программирования. Рассмотрим операцию, в которой должен участвовать каждый элемент списка. Это можно сделать рекурсивно, т. е. сначала обработать начало списка, затем перейти к хвосту — более короткому списку, состоящему из первоначального списка без первого элемента, а потом снова перейти на следующий уровень рекурсии.

Для написания такой рекурсивной функции используется оператор (`::`) в сопоставлении шаблонов, который позволяет отделить начало списка от хвоста.

Следующий пример кода показывает, как использовать сопоставление шаблонов для реализации рекурсивной функции, выполняющей операции над списком.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

Предыдущий код хорошо работает для небольших списков, но при работе со списками большого размера может случиться переполнение стека. Следующий код улучшает предыдущий за счет использования аргумента аккумулирования — это стандартная техника работы с рекурсивными функциями. Использование аргумента аккумулирования делает функцию рекурсивной по отношению к хвосту, что экономит место в стеке.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

Функция `RemoveAllMultiples` — это рекурсивная функция, которая обрабатывает два списка. Первый список содержит цифры, кратные которым будут удалены, а второй представляет собой список, из которого будут удаляться цифры. Код в следующем примере использует рекурсивную функцию для удаления всех непростых чисел из списка. После его выполнения в списке остаются только простые числа.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

Вывод выглядит следующим образом.

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a>Функции модуля

[Модуль List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) предоставляет функции, которые обращаются к элементам списка. Самым легким и быстрым для доступа является первоначальный элемент. Используйте [заголовок](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) свойства или список функций модуля [. Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head). Можно получить доступ к заключительному фрагменту списка с помощью свойства [tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) или функции [List. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) . Чтобы найти элемент по индексу, используйте функцию [List. nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) . `List.nth` проходит по списку. Таким образом, это O (*n*). Если в коде часто используется `List.nth`, то вместо списка можно использовать массив. Доступ к элементам массива осуществляется через O(1).

### <a name="boolean-operations-on-lists"></a>Логические операции со списками

Функция [List. isEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) определяет, содержит ли список какие-либо элементы.

Функция [List. Exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) применяет логический тест к элементам списка и возвращает значение `true` , если какой-либо элемент удовлетворяет данному тесту. [List. exists2-](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) аналогичен, но работает с последовательными парами элементов в двух списках.

В следующем коде показано использование функции `List.exists`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

Вывод выглядит следующим образом.

```console
For list [0; 1; 2; 3], contains zero is true
```

В следующем примере показано использование функции `List.exists2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

Вывод выглядит следующим образом.

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

[List. forall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) можно использовать, если требуется проверить, соответствуют ли все элементы списка условию.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

Вывод выглядит следующим образом.

```console
true
false
```

Аналогичным образом [List. forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) определяет, соответствуют ли все элементы в соответствующих позициях в двух списках логическому выражению, включающему в себя каждую пару элементов.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

Вывод выглядит следующим образом.

```console
true
false
```

### <a name="sort-operations-on-lists"></a>Операции сортировки списков

Функции [List. Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List. sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)и [List. сортвис](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) сортируют списки сортировки. Функция сортировки определяет, какую из этих трех функций использовать. `List.sort` использует универсальное сравнение по умолчанию. Общее сравнение выполняется с помощью глобальных операторов на основе функции общего сравнения значений. Оно эффективно работает с различными типами элементов, такими как числовые типы, кортежи, записи, размеченные объединения, списки, массивы и любой другой тип, включающий `System.IComparable`. Для типов, включающих `System.IComparable`, общее сравнение выполняется с помощью функции `System.IComparable.CompareTo()`. Общее сравнение также работает со строками, но использует культурно-независимый порядок сортировки. Общее сравнение не следует применять к неподдерживаемым типам, например типам функций. К тому же выполнение общего сравнения по умолчанию лучше всего подходит для слабо структурированных типов. Для сильно структурированных типов, которые необходимо часто сравнивать и сортировать, можно использовать функцию `System.IComparable` и метод `System.IComparable.CompareTo()`.

`List.sortBy` принимает функцию, которая возвращает значение, используемое в качестве критерия сортировки, и `List.sortWith` принимает в качестве аргумента функцию сравнения. Две последние функции полезны при работе с типами, которые не поддерживают сравнение, а также если сравнение требует более сложной семантики, например в случае со строками, учитывающими язык и регион.

В следующем примере показано использование функции `List.sort`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

Вывод выглядит следующим образом.

```console
[-2; 1; 4; 5; 8]
```

В следующем примере показано использование функции `List.sortBy`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

Вывод выглядит следующим образом.

```console
[1; -2; 4; 5; 8]
```

В следующем примере показано использование `List.sortWith`. В этом примере обычная функция сравнения `compareWidgets` используется сначала для сравнения одного поля пользовательского типа, а затем другого, если значения первого поля равны.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

Вывод выглядит следующим образом.

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a>Операции поиска в списках

Списки поддерживают различные операции поиска. Простейшая функция [List. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find)позволяет найти первый элемент, соответствующий заданному условию.

В следующем примере кода показано, как использовать `List.find` для поиска первого числа в списке, которое делится на 5.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

Результат — 5.

Если элементы должны быть преобразованы первыми, вызовите [List. Pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), который принимает функцию, возвращающую параметр, и ищет первое значение параметра, равное `Some(x)` . Вместо возвращения элемента функция `List.pick` возвращает результат `x`. Если совпадения не найдены, функция `List.pick` возвращает `System.Collections.Generic.KeyNotFoundException`. В следующем коде показано использование `List.pick`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

Вывод выглядит следующим образом.

```console
"b"
```

Другая группа операций поиска, [List. tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) и связанных функций, возвращает значение параметра. Функция `List.tryFind` возвращает первый элемент списка, который удовлетворяет условию, если такой элемент есть, и значение параметра `None`, если нет. Список вариантов [. tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) возвращает индекс элемента, если он найден, а не сам элемент. Эти функции представлены в следующем коде.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

Вывод выглядит следующим образом.

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a>Арифметические операции со списками

Общие арифметические операции, такие как Sum и Average, встроены в [модуль List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html). Для работы с [List. Sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum)тип элемента списка должен поддерживать `+` оператор и иметь нулевое значение. Все встроенные арифметические типы удовлетворяют этим условиям. Для работы с [List. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average)тип элемента должен поддерживать деление без остатка, который исключает целочисленные типы, но допускает типы с плавающей запятой. Функции [List. sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) и [List. averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) принимают в качестве параметра функцию, а результаты этой функции используются для вычисления значений суммы или среднего значения.

В следующем коде показано использование `List.sum`, `List.sumBy` и `List.average`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

Результат выглядит так: `1.000000`.

В следующем коде показано использование `List.averageBy`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

Результат выглядит так: `5.5`.

### <a name="lists-and-tuples"></a>Списки и кортежи

Для работы со списками, содержащими кортежи, можно использовать функции упаковки и распаковки. Они объединяют два списка с одним значением в один список кортежей или разбивают один список кортежей на два списка с одним значением. Самая простая функция [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) принимает два списка отдельных элементов и создает один список пар кортежей. Другая версия, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), принимает три списка отдельных элементов и создает один список кортежей с тремя элементами. В следующем коде показано использование функции `List.zip`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

Вывод выглядит следующим образом.

```console
[(1, -1); (2, -2); (3; -3)]
```

В следующем коде показано использование функции `List.zip3`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

Вывод выглядит следующим образом.

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

Соответствующие версии распаковать, [List. unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) и [List. unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), принимают списки кортежей и возвращаемых списков в кортеже, где первый список содержит все элементы, которые были первыми в каждом кортеже, а второй список содержит второй элемент каждого кортежа и т. д.

В следующем примере кода показано использование [List. unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

Вывод выглядит следующим образом.

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

В следующем примере кода показано использование [List. unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

Вывод выглядит следующим образом.

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a>Операции с элементами списка

F# поддерживает различные операции с элементами списка. Самый простой — [List. iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), который позволяет вызывать функцию для каждого элемента списка. Варианты включают [List. iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), который позволяет выполнить операцию над элементами двух списков, [List. iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), которая похожа на `List.iter` , за исключением того, что индекс каждого элемента передается в качестве аргумента функции, которая вызывается для каждого элемента, и [List. iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), являющийся сочетанием функций `List.iter2` и `List.iteri` . Эти функции показаны в следующем примере кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

Вывод выглядит следующим образом.

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

Другой часто используемой функцией, которая преобразует элементы списка, является [List. Map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), которая позволяет применить функцию к каждому элементу списка и поместит все результаты в новый список. [List. map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) и [List. map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) — это варианты, принимающие несколько списков. Можно также использовать [List. MAPI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) и [List. mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), если в дополнение к элементу, функции необходимо передать индекс каждого элемента. Единственное различие между `List.mapi2` и `List.mapi` состоит в том, что функция `List.mapi2` работает с двумя списками. В следующем примере показан [List. Map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

Вывод выглядит следующим образом.

```console
[2; 3; 4]
```

В следующем примере показано использование `List.map2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

Вывод выглядит следующим образом.

```console
[5; 7; 9]
```

В следующем примере показано использование `List.map3`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

Вывод выглядит следующим образом.

```console
[7; 10; 13]
```

В следующем примере показано использование `List.mapi`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

Вывод выглядит следующим образом.

```console
[1; 3; 5]
```

В следующем примере показано использование `List.mapi2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

Вывод выглядит следующим образом.

```console
[0; 7; 18]
```

[List. собирающий](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) аналогичен `List.map` , за исключением того, что каждый элемент создает список, а все эти списки объединяются в окончательный список. В следующем коде каждый элемент списка генерирует три числа. Все они собираются в один список.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

Вывод выглядит следующим образом.

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

Можно также использовать [List. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), который принимает логическое условие и создает новый список, состоящий только из элементов, которые соответствуют заданному условию.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

Результатом является список `[2; 4; 6]`.

Сочетание Map и Filter, [List. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) позволяет одновременно преобразовывать и выбирать элементы. `List.choose` применяет функцию, возвращающую параметр для каждого элемента списка, и возвращает новый список результатов для элементов, когда функция возвращает значение параметра `Some` .

В следующем коде показано использование функции `List.choose` для выбора из списка слов с заглавными буквами.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

Вывод выглядит следующим образом.

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a>Операции с несколькими списками

Списки могут быть объединены. Чтобы объединить два списка в один, используйте [List. append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append). Для объединения более двух списков используйте [List. Concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a>Операции сворачивания и сканирования

Некоторые операции со списками включают взаимозависимости между всеми элементами списка. Операции свертывания и сканирования подобны `List.iter` и `List.map` в том, что вы вызываете функцию для каждого элемента, но эти операции предоставляют дополнительный параметр, называемый *накопительным* , который передает информацию через вычисления.

`List.fold` можно использовать для выполнения расчетов со списком.

В следующем примере кода показано использование [List. fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) для выполнения различных операций.

Лист обходится. Аккумулятор `acc` — это значение, которое передается дальше, пока продолжается расчет. Первый аргумент забирает аккумулятор и элемент списка и возвращает промежуточный результат расчета для этого элемента списка. Второй аргумент является исходным значением аккумулятора.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

Версии этих функций с цифрой в имени функции работают с несколькими списками. Например, [List. fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) выполняет вычисления в двух списках.

В следующем примере показано использование функции `List.fold2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

`List.fold` и [List. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) различаются в, `List.fold` возвращающие окончательное значение дополнительного параметра, но `List.scan` возвращает список промежуточных значений (вместе с окончательным значением) дополнительного параметра.

Каждая из этих функций включает обратную вариацию, например [List. foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), которая отличается в порядке обхода списка и порядком аргументов. Кроме того, `List.fold` и `List.foldBack` имеют варианты [List. fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) и [List. foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), которые принимают два списка одинаковой длины. Функция, которая выполняется по каждому элементу, может использовать соответствующие элементы обоих списков для выполнения некоторых действий. Типы элементов этих списков могут отличаться, как в следующем примере, где один список содержит суммы транзакций на банковском счете, а другой — типы транзакций (внесение или снятие).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

При расчете суммы функции `List.fold` и `List.foldBack` действуют одинаково, так как результат не зависит от порядка обхода. В следующем примере кода функция `List.foldBack` используется для добавления элемента в список.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

В следующем примере снова используется банковский счет. В этот раз добавляется новый тип транзакций: расчет процентов. Конечный баланс теперь зависит от порядка транзакций.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

Список функций [. reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) в некоторой степени аналогичен `List.fold` и `List.scan` , за исключением того, что вместо того, чтобы передавать отдельный агрегат, `List.reduce` принимает функцию, которая принимает два аргумента типа элемента, а не только один, а один из этих аргументов выступает в качестве совокупного, то есть сохраняет промежуточный результат вычисления. `List.reduce` начинается с работы на первых двух элементах списка, а затем использует результат операции вместе со следующим элементом. Так как здесь нет отдельного аккумулятора с собственным типом, функция `List.reduce` может использоваться вместо `List.fold` только в том случае, если аккумулятор и элемент имеют одинаковые типы. В следующем коде показано использование функции `List.reduce`. `List.reduce` создает исключение, если предоставленный список не содержит элементов.

В следующем коде первый вызов лямбда-выражения дает аргументы 2 и 4 и возвращает 6. В следующем вызове даются аргументы 6 и 10 и возвращается результат 16.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a>Конвертация списков и другие типы коллекций

Модуль `List` предоставляет функции для прямой и обратной конвертации обоих последовательностей и массивов. Для преобразования в последовательность или из последовательности используйте [List. toSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) или [List. ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq). Для преобразования в массив или из массива используйте [List. ToArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) или [List. офаррай](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).

### <a name="additional-operations"></a>Дополнительные операции

Дополнительные сведения о дополнительных операциях [со списками см. в](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)разделе Справочник по библиотекам.

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Типы языка F#](fsharp-types.md)
- [Последовательности](sequences.md)
- [Массивы](arrays.md)
- [Параметры](options.md)
