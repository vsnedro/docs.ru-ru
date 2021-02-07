---
description: Дополнительные сведения о предложении WHERE (Visual Basic)
title: Предложение Where
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 11f9a7e586a1fdea826df4fb34a7227747c8cebd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730321"
---
# <a name="where-clause-visual-basic"></a>Предложение Where (Visual Basic)

Задает условие фильтрации для запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>Компоненты  

 `condition`  
 Обязательный элемент. Выражение, определяющее, включаются ли значения для текущего элемента в коллекции в выходную коллекцию. Выражение должно иметь `Boolean` значение или эквивалент `Boolean` значения. Если условие принимает значение `True` , элемент включается в результат запроса; в противном случае элемент исключается из результата запроса.  
  
## <a name="remarks"></a>Remarks  

 `Where`Предложение позволяет фильтровать данные запроса, выбирая только те элементы, которые соответствуют определенным условиям. Элементы, значения которых приводят к `Where` вычислению предложения `True` , включаются в результат запроса; другие элементы исключаются. Выражение, используемое в `Where` предложении, должно возвращать значение `Boolean` или эквивалент типа `Boolean` , например целое число, которое вычисляется, `False` если его значение равно нулю. В предложении можно объединить несколько выражений, `Where` используя логические операторы, такие как `And` ,, `Or` ,, `AndAlso` `OrElse` `Is` и `IsNot` .  
  
 По умолчанию выражения запроса не оцениваются до тех пор, пока они не будут доступны, например, когда они привязаны к данным или просматриваются в `For` цикле. В результате это `Where` предложение не вычисляется до тех пор, пока не будет осуществлен доступ к запросу. При наличии внешних значений для запроса, которые используются в `Where` предложении, убедитесь, что в `Where` предложении во время выполнения запроса используется соответствующее значение. Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Можно вызывать функции внутри предложения, `Where` чтобы выполнить вычисление или операцию над значением из текущего элемента в коллекции. Вызов функции в `Where` предложении может привести к немедленному выполнению запроса, если он определен, а не при обращении к нему. Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Пример  

 Следующее выражение запроса использует `From` предложение для объявления переменной диапазона `cust` для каждого `Customer` объекта в `customers` коллекции. `Where`Предложение использует переменную диапазона для ограничения выходных данных для клиентов из указанной области. `For Each`Цикл отображает название компании для каждого клиента в результатах запроса.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Пример  

 В следующем примере используются `And` и `Or` логические операторы в `Where` предложении.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение From](from-clause.md)
- [Предложение SELECT](select-clause.md)
- [Оператор For Each…Next](../statements/for-each-next-statement.md)
