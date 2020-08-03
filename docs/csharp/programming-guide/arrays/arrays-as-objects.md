---
title: Руководство по программированию на C#. Массивы как объекты
description: В C# массивы представляют собой объекты массива абстрактного базового типа. Можно использовать свойства и другие члены класса массива, например свойство Length.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 984def3ef74b07d7099fae6cae6d6f8ce7e03e12
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474726"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Массивы как объекты (Руководство по программированию на C#)

В C# массивы представляют собой реальные объекты, а не просто адресуемые области непрерывной памяти, как в C и C++. <xref:System.Array> — это абстрактный базовый тип для всех типов массивов. Вы можете использовать свойства и другие члены класса, входящие в <xref:System.Array>. Например, с помощью свойства <xref:System.Array.Length%2A> можно получить длину массива. В следующем коде значение длины массива `numbers` (`5`) присваивается переменной с именем `lengthOfNumbers`:

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

В классе <xref:System.Array> представлено множество других полезных методов и свойств для сортировки, поиска и копирования массивов.

## <a name="example"></a>Пример

В этом примере используется свойство <xref:System.Array.Rank%2A>, позволяющее отобразить число измерений массива.

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Массивы](./index.md)
- [Одномерные массивы](./single-dimensional-arrays.md)
- [Многомерные массивы](./multidimensional-arrays.md)
- [Массивы массивов](./jagged-arrays.md)
