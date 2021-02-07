---
description: 'Дополнительные сведения: итератор (Visual Basic)'
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 7a3329ba23a3f2487343b332f3bb9c4b19c36496
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730529"
---
# <a name="iterator-visual-basic"></a>Итератор (Visual Basic)

Указывает, что функция или `Get` метод доступа являются итератором.  
  
## <a name="remarks"></a>Remarks  

 *Итератор* выполняет настраиваемую итерацию по коллекции. Итератор использует оператор [yield](../statements/yield-statement.md) для возвращения каждого элемента в коллекции по одному за раз. При `Yield` достижении оператора текущее место в коде сохраняется. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Итератор может быть реализован в виде функции или `Get` метода доступа к определению свойства. `Iterator`Модификатор отображается в объявлении функции итератора или `Get` метода доступа.  
  
 Итератор вызывается из клиентского кода с помощью метода [For Each... Следующий оператор](../statements/for-each-next-statement.md).  
  
 Тип возвращаемого значения функции итератора или `Get` метода доступа может быть <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601> .  
  
 Итератор не может иметь `ByRef` параметров.  
  
 Итератор не может использоваться в событии, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.  
  
 Итератор может быть анонимной функцией. Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Использование  

 Модификатор `Iterator` можно использовать в следующих контекстах:  
  
- [Оператор Function](../statements/function-statement.md)  
  
- [Property Statement](../statements/property-statement.md)  
  
## <a name="example"></a>Пример  

 В следующем примере демонстрируется функция итератора. Функция итератора содержит `Yield` оператор, который находится внутри блока [for... Следующий](../statements/for-next-statement.md) цикл. Каждая итерация тела оператора [for each](../statements/for-each-next-statement.md) в `Main` создает вызов `Power` функции итератора. При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Пример  

 В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор. `Iterator`Модификатор находится в объявлении свойства.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Дополнительные примеры см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Итераторы](../../programming-guide/concepts/iterators.md)
- [Оператор Yield](../statements/yield-statement.md)
