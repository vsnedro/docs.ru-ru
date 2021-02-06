---
description: 'Дополнительные сведения о предложении: Take (Visual Basic)'
title: Предложение Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 6542d262490d9d4acff893b2a99ffb60dd1446a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653541"
---
# <a name="take-clause-visual-basic"></a>Предложение Take (Visual Basic)

Возвращает указанное число идущих подряд элементов с начала коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Компоненты  

 `count`  
 Обязательный элемент. Значение или выражение, результатом которого является число возвращаемых элементов последовательности.  
  
## <a name="remarks"></a>Remarks  

 `Take`Предложение вызывает включение в запрос указанного числа смежных элементов из начала списка результатов. Число включаемых элементов задается `count` параметром.  
  
 `Take`Предложение с `Skip` предложением можно использовать для возврата диапазона данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона в `Skip` предложение и размер диапазона в `Take` предложение. В этом случае `Take` предложение должно быть указано после `Skip` предложения.  
  
 При использовании `Take` предложения в запросе может также потребоваться убедиться, что результаты возвращены в порядке, который позволит `Take` предложению включить предполагаемые результаты. Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](order-by-clause.md).  
  
 С помощью предложения можно `TakeWhile` указать, что возвращаются только определенные элементы, в зависимости от указанного условия.  
  
## <a name="example"></a>Пример  

 В следующем примере кода предложение используется `Take` вместе с `Skip` предложением для возврата данных из запроса на страницах. Функция "клиенты" использует `Skip` предложение для обхода клиентов в списке до получения значения начального индекса и использует `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение From](from-clause.md)
- [Предложение ORDER BY](order-by-clause.md)
- [Предложение Take While](take-while-clause.md)
- [Предложение Skip](skip-clause.md)
