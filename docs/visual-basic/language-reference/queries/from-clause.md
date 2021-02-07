---
description: Дополнительные сведения о предложении FROM (Visual Basic)
title: Предложение From
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: e35188412deb7fd9f2d8306c85057d050a60d030
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700563"
---
# <a name="from-clause-visual-basic"></a>Предложение From (Visual Basic)

Указывает одну или несколько переменных диапазона и коллекцию для запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`element`|Обязательный. *Переменная диапазона* , используемая для прохода по элементам коллекции. Переменная диапазона используется для ссылки на каждый элемент в, `collection` когда запрос выполняет итерацию по `collection` . Должен быть перечислимым типом.|  
|`type`|Необязательный элемент. Тип параметра `element`. Если не `type` указано, тип `element` выводится из `collection` .|  
|`collection`|Обязательный элемент. Ссылается на коллекцию, к которой выполняется запрос. Должен быть перечислимым типом.|  
  
## <a name="remarks"></a>Remarks  

 `From`Предложение используется для указания исходных данных для запроса и переменных, которые используются для ссылки на элемент из исходной коллекции. Эти переменные называются *переменными диапазона*. `From`Предложение является обязательным для запроса, за исключением случаев, когда `Aggregate` предложение используется для задания запроса, возвращающего только агрегированные результаты. Дополнительные сведения см. в разделе [предложение Aggregate](aggregate-clause.md).  
  
 В запросе можно указать несколько `From` предложений, чтобы определить несколько коллекций для объединения. Если указано несколько коллекций, они проходят по отдельности или объединяются, если они связаны. Коллекции можно объединять неявным образом с помощью `Select` предложения или явно с помощью `Join` предложений или `Group Join` . В качестве альтернативы можно указать несколько переменных диапазона и коллекций в одном `From` предложении, при этом каждая связанная переменная диапазона и коллекция, отделенные друг от друга запятыми. В следующем примере кода показаны оба синтаксических параметра для `From` предложения.  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 `From`Предложение определяет область запроса, аналогичную области `For` цикла. Таким образом, каждая `element` переменная диапазона в области запроса должна иметь уникальное имя. Поскольку можно указать несколько `From` предложений для запроса, последующие `From` предложения могут ссылаться на переменные диапазона в `From` предложении или они могут ссылаться на переменные диапазона в предыдущем `From` предложении. Например, в следующем примере показано вложенное `From` предложение, где коллекция во втором предложении основана на свойстве переменной диапазона в первом предложении.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 `From`За каждым предложением может следовать любое сочетание дополнительных предложений запроса для уточнения запроса. Запрос можно уточнить следующими способами.  
  
- Объедините несколько коллекций неявным образом с помощью `From` `Select` предложений и или явно с помощью `Join` предложений или `Group Join` .  
  
- Используйте `Where` предложение для фильтрации результатов запроса.  
  
- Отсортируйте результат с помощью `Order By` предложения.  
  
- Группировать аналогичные результаты вместе с помощью `Group By` предложения.  
  
- Используйте `Aggregate` предложение для определения агрегатных функций для вычисления результата всего запроса.  
  
- Используйте `Let` предложение, чтобы ввести переменную итерации, значение которой определяется выражением, а не коллекцией.  
  
- Используйте `Distinct` предложение для пропуска повторяющихся результатов запроса.  
  
- Выявление частей результата, возвращаемых с помощью `Skip` предложений, `Take` , `Skip While` и `Take While` .  
  
## <a name="example"></a>Пример  

 Следующее выражение запроса использует `From` предложение для объявления переменной диапазона `cust` для каждого `Customer` объекта в `customers` коллекции. `Where`Предложение использует переменную диапазона для ограничения выходных данных для клиентов из указанной области. `For Each`Цикл отображает название компании для каждого клиента в результатах запроса.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>См. также

- [Запросы](index.md)
- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Оператор For Each…Next](../statements/for-each-next-statement.md)
- [Оператор For…Next](../statements/for-next-statement.md)
- [Предложение SELECT](select-clause.md)
- [Предложение WHERE](where-clause.md)
- [Aggregate Clause](aggregate-clause.md)
- [Предложение Distinct](distinct-clause.md)
- [Предложение Join](join-clause.md)
- [Предложение Group Join](group-join-clause.md)
- [Предложение ORDER BY](order-by-clause.md)
- [Предложение Let](let-clause.md)
- [Предложение Skip](skip-clause.md)
- [Предложение Take](take-clause.md)
- [Предложение Skip While](skip-while-clause.md)
- [Предложение Take While](take-while-clause.md)
