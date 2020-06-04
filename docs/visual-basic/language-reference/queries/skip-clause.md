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
ms.openlocfilehash: 427d14453260a54bd3f2ab9a8ac75dedacd291f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359662"
---
# <a name="skip-clause-visual-basic"></a>Предложение Skip (Visual Basic)
Пропускает заданное число элементов в коллекции и возвращает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>Компоненты  
 `count`  
 Обязательный. Значение или выражение, результатом которого является число пропускаемых элементов последовательности.  
  
## <a name="remarks"></a>Комментарии  
 `Skip`Предложение заставляет запрос обходить элементы в начале списка результатов и возвращать оставшиеся элементы. Число пропускаемых элементов определяется `count` параметром.  
  
 `Skip`Предложение с `Take` предложением можно использовать для возврата диапазона данных из любого сегмента запроса. Для этого передайте индекс первого элемента диапазона в `Skip` предложение и размер диапазона в `Take` предложение.  
  
 При использовании `Skip` предложения в запросе может также потребоваться убедиться, что результаты возвращаются в порядке, который позволит `Skip` использовать предложение для обхода предполагаемых результатов. Дополнительные сведения о упорядочении результатов запроса см. в разделе [предложение ORDER BY](order-by-clause.md).  
  
 Можно использовать предложение, `SkipWhile` чтобы указать, что игнорируются только определенные элементы, в зависимости от указанного условия.  
  
## <a name="example"></a>Пример  
 В следующем примере кода предложение используется `Skip` вместе с `Take` предложением для возврата данных из запроса на страницах. `GetCustomers`Функция использует `Skip` предложение для обхода клиентов в списке до получения значения начального индекса и использует `Take` предложение для возврата страницы клиентов, начиная с этого значения индекса.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
- [Предложение Order By](order-by-clause.md)
- [Предложение Skip While](skip-while-clause.md)
- [Предложение Take](take-clause.md)
