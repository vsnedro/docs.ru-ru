---
title: Руководство по программированию на C#. Использование оператора foreach с массивами
description: Оператор foreach в C# выполняет итерацию по элементам массива. Для одномерных массивов оператор foreach обрабатывает элементы в порядке возрастания индекса.
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: d924a3ef3351cbb30b809a1542f35314ee721852
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474544"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Использование оператора foreach с массивами (Руководство по программированию на C#)

Оператор [foreach](../../language-reference/keywords/foreach-in.md) обеспечивает простой и понятный способ итерации по элементам массива или любой перечислимой коллекции.

Для одномерных массивов оператор `foreach` обрабатывает элементы в порядке возрастания индекса, начиная с индекса 0 и заканчивая индексом `Length - 1`:

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

Для многомерных массивов элементов обрабатываются так, что сначала увеличиваются индексы крайнего правого измерения, а затем — следующего левого и т. д. влево:

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

Тем не менее для управления порядком обрабатываемых элементов в многомерных массивах можно использовать вложенный цикл [for](../../language-reference/keywords/for.md).

## <a name="see-also"></a>См. также

- <xref:System.Array>
- [Руководство по программированию на C#](../index.md)
- [Массивы](index.md)
- [Одномерные массивы](single-dimensional-arrays.md)
- [Многомерные массивы](multidimensional-arrays.md)
- [Массивы массивов](jagged-arrays.md)
