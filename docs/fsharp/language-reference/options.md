---
title: Параметры
description: 'Узнайте, как использовать типы параметров F #, если фактическое значение для именованного значения или переменной может не существовать.'
ms.date: 08/13/2020
ms.openlocfilehash: 0618590c10f6ecac51a23483ca0ab6cd66f2df4f
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557572"
---
# <a name="options"></a>Параметры

Тип параметра в F # используется, если фактическое значение для именованного значения или переменной может не существовать. Параметр имеет базовый тип и может содержать значение этого типа или не может иметь значения.

## <a name="remarks"></a>Remarks

В следующем коде показана функция, которая создает тип параметра.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Как видите, создается значение, если входные данные `a` больше 0 `Some(a)` .  В противном случае `None` создается.

Значение `None` используется, если параметр не имеет фактического значения. В противном случае выражение `Some( ... )` дает параметру значение. Значения `Some` и `None` полезны при сопоставлении шаблонов, как в следующей функции `exists` , которая возвращает, `true` Если параметр имеет значение, а `false` Если нет.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Использование параметров

Параметры обычно используются, если поиск не возвращает соответствующий результат, как показано в следующем коде.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

В приведенном выше коде рекурсивный поиск по списку выполняется рекурсивно. Функция `tryFindMatch` принимает функцию предиката `pred` , которая возвращает логическое значение, и список для поиска. Если найден элемент, удовлетворяющий предикату, рекурсия завершается, а функция возвращает значение в виде параметра в выражении `Some(head)` . Рекурсия завершается при сопоставлении пустого списка. В этот момент значение `head` не было найдено и `None` возвращается.

Многие функции библиотеки F #, которые выполняют поиск в коллекции значений, которые могут быть или не существуют, возвращают `option` тип. По соглашению эти функции начинаются с `try` префикса, например [`Seq.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex) .

Параметры также могут быть полезны, если значение может не существовать, например, если возможно, что при попытке создания значения возникнет исключение. Это показано в следующем примере кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

`openFile`Функция в предыдущем примере имеет тип `string -> File option` , так как она возвращает `File` объект, если файл открыт успешно, и `None` Если возникает исключение. В зависимости от ситуации может не подходить к перехвату исключения, а не разрешать его распространение.

Кроме того, по-прежнему можно передать `null` или значение, равное NULL, в `Some` случае параметра. Обычно это следует избегать, и обычно это выполняется в обычной программе программирования на F #, но это возможно из-за природы ссылочных типов в .NET.

## <a name="option-properties-and-methods"></a>Свойства и методы параметров

Тип параметра поддерживает следующие свойства и методы.

|Свойство или метод|Тип|Описание|
|------------------|----|-----------|
|[None](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#None)|`'T option`|Статическое свойство, которое позволяет создать значение параметра, имеющее `None` значение.|
|[Не задано](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsNone)|`bool`|Возвращает, `true` Если параметр имеет `None` значение.|
|[Часть](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsSome)|`bool`|Возвращает `true` , если параметр имеет значение, не равное `None` .|
|[Некоторых](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Some)|`'T option`|Статический член, создающий параметр, который имеет значение, не равное `None` .|
|[Значение](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Value)|`'T`|Возвращает базовое значение или создает исключение, `System.NullReferenceException` Если значение равно `None` .|

## <a name="option-module"></a>Модуль параметров

Существует модуль, [параметр](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html), содержащий полезные функции, которые выполняют операции с параметрами. Некоторые функции позволяют повторить функциональность свойств, но они полезны в контекстах, где требуется функция. [Option. some](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isSome) и [Option. None](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isNone) являются функциями модуля, которые проверяют, содержит ли параметр значение. [Параметр. Get](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#get) получает значение, если таковое имеется. Если значение отсутствует, вызывается исключение `System.ArgumentException` .

Функция [Option. Bind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#bind) выполняет функцию для значения, если имеется значение. Функция должна принимать ровно один аргумент, и ее тип параметра должен быть типом параметра. Возвращаемое значение функции является другим типом параметра.

Модуль Option также включает функции, которые соответствуют функциям, доступным для списков, массивов, последовательностей и других типов коллекций. К этим функциям относятся [`Option.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#map) ,,,, [`Option.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#iter) [`Option.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#forall) [`Option.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#exists) [`Option.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#foldBack) , [`Option.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#fold) и [`Option.count`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#count) . Эти функции позволяют использовать параметры как коллекцию с нулевым или одним элементом. Дополнительные сведения и примеры см. в обсуждении функций сбора в [списках](lists.md).

## <a name="converting-to-other-types"></a>Преобразование в другие типы

Параметры можно преобразовать в списки или массивы. При преобразовании параметра в любую из этих структур данных Результирующая структура данных не может содержать ни одного элемента. Чтобы преобразовать параметр в массив, используйте [`Option.toArray`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toArray) . Чтобы преобразовать параметр в список, используйте [`Option.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toList) .

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Типы языка F#](fsharp-types.md)
