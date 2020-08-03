---
title: Руководство по программированию на C#. Одномерные массивы
description: Создайте одномерный массив в C#, используя оператор new и указав тип элементов массива и число элементов.
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: ada01262d57cbfebc8bfa1a5fee0639a10db5a4b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474596"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Одномерные массивы (Руководство по программированию на C#)

Для создания одномерного массива используется оператор [new](../../language-reference/operators/new-operator.md) и указывается тип элементов массива и число элементов. В следующем примере показано объявление массива, содержащего пять целых чисел:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

Этот массив содержит элементы с `array[0]` по `array[4]`. Элементы массива элементы инициализируются до значения по умолчанию для типа элемента. Для целых чисел это `0`.

Массивы могут хранить любой указанный тип элемента. Например, в следующем примере приводится объявление массива строк:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a>Инициализация массива

Элементы массива можно инициализировать при объявлении. В этом случае не требуется спецификатор длины, поскольку он уже задан по числу элементов в списке инициализации. Пример:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

Ниже приведено объявление массива строк, где каждый элемент массива инициализируется с использованием названия дня:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
Если массив инициализируется при объявлении, можно не использовать выражение `new` и тип массива, как показано в следующем коде. Такой массив называется [неявно типизированным](implicitly-typed-arrays.md):

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

Переменную массива можно объявить без ее создания, но при присвоении нового массива этой переменной необходимо использовать оператор `new`. Пример:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a>Массивы типов значений и ссылочных типов

Рассмотрим следующее объявление массива:  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

Результат этого оператора зависит от того, является ли `SomeType` типом значения или ссылочным типом. Если это тип значения, оператор создает массив из 10 элементов, каждый из которых имеет тип `SomeType`. Если `SomeType` является ссылочным типом, этот оператор создает массив из 10 элементов, каждый из которых инициализируется с использованием ссылки NULL. В обоих случаях элементы инициализируются до значения по умолчанию для типа элемента. См. дополнительные сведения о [типах значений](../../language-reference/builtin-types/value-types.md) и [ссылочных типах](../../language-reference/keywords/reference-types.md).
  
## <a name="see-also"></a>См. также

- <xref:System.Array>
- [Массивы](./index.md)
- [Многомерные массивы](./multidimensional-arrays.md)
- [Массивы массивов](./jagged-arrays.md)
