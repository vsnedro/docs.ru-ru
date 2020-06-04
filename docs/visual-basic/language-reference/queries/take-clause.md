---
title: Предложение Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 25dd06905525a96bc1504f033eb4f19af6d454a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359636"
---
# <a name="take-clause-visual-basic"></a>Предложение Take (Visual Basic)
Возвращает указанное число идущих подряд элементов с начала коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Компоненты  
 `count`  
 Обязательный. Значение или выражение, результатом которого является число возвращаемых элементов последовательности.  
  
## <a name="remarks"></a>Комментарии  
 `Take`Предложение вызывает включение в запрос указанного числа смежных элементов из начала списка результатов. Число включаемых элементов задается `count` параметром.  
  
 `Take`Предложение с `Skip` предложением можно использовать для возврата диапазона данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона в `Skip` предложение и размер диапазона в `Take` предложение. В этом случае `Take` предложение должно быть указано после `Skip` предложения.  
  
 При использовании `Take` предложения в запросе может также потребоваться убедиться, что результаты возвращены в порядке, который позволит `Take` предложению включить предполагаемые результаты. Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](order-by-clause.md).  
  
 С помощью предложения можно `TakeWhile` указать, что возвращаются только определенные элементы, в зависимости от указанного условия.  
  
## <a name="example"></a>Пример  
 В следующем примере кода предложение используется `Take` вместе с `Skip` предложением для возврата данных из запроса на страницах. Функция "клиенты" использует `Skip` предложение для обхода клиентов в списке до получения значения начального индекса и использует `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
- [Предложение Order By](order-by-clause.md)
- [Предложение Take While](take-while-clause.md)
- [Предложение Skip](skip-clause.md)
