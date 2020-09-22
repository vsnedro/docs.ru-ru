---
title: Предложение Skip
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 40e89160baf663f7d6785e5d3e09ad6cc4eefbde
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866303"
---
# <a name="skip-clause-visual-basic"></a>Предложение Skip (Visual Basic)

Пропускает заданное число элементов в коллекции и возвращает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>Компоненты  

 `count`  
 Обязательный элемент. Значение или выражение, результатом которого является число пропускаемых элементов последовательности.  
  
## <a name="remarks"></a>Remarks  

 `Skip`Предложение заставляет запрос обходить элементы в начале списка результатов и возвращать оставшиеся элементы. Число пропускаемых элементов определяется `count` параметром.  
  
 `Skip`Предложение с `Take` предложением можно использовать для возврата диапазона данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона в `Skip` предложение и размер диапазона в `Take` предложение.  
  
 При использовании `Skip` предложения в запросе может также потребоваться убедиться, что результаты возвращаются в порядке, который позволит `Skip` использовать предложение для обхода предполагаемых результатов. Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](order-by-clause.md).  
  
 Можно использовать предложение, `SkipWhile` чтобы указать, что игнорируются только определенные элементы, в зависимости от указанного условия.  
  
## <a name="example"></a>Пример  

 В следующем примере кода предложение используется `Skip` вместе с `Take` предложением для возврата данных из запроса на страницах. `GetCustomers`Функция использует `Skip` предложение для обхода клиентов в списке до получения значения начального индекса и использует `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
- [Предложение ORDER BY](order-by-clause.md)
- [Предложение Skip While](skip-while-clause.md)
- [Предложение Take](take-clause.md)
