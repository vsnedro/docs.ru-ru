---
description: Дополнительные сведения см. в статье как сортировать массив в Visual Basic
title: Практическое руководство. Сортировка массива
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: ea030b63dbbb5f5ea1d6160757afe2e9b58f7c21
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462767"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Как сортировать массив в Visual Basic

В этой статье показан пример сортировки массива строк в Visual Basic.

## <a name="example"></a>Пример

В этом примере объявляется массив `String` объектов с именем `zooAnimals` , заполняется, а затем сортируется по алфавиту:
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a>Отказоустойчивость

При следующих условиях возможно возникновение исключения:

- Массив пуст ( <xref:System.ArgumentNullException> класс).
- Массив является многомерным ( <xref:System.RankException> классом).
- Один или несколько элементов массива не реализуют <xref:System.IComparable> интерфейс ( <xref:System.InvalidOperationException> класс).

## <a name="see-also"></a>См. также

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Массивы](index.md)
- [Устранение неполадок, связанных с массивами](troubleshooting-arrays.md)
- [Коллекции](../../concepts/collections.md)
- [Оператор For Each…Next](../../../language-reference/statements/for-each-next-statement.md)
