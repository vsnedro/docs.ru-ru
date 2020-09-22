---
title: Предложение Order By
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 05fa720237f4b0185b5c07217362c99b5dbf4303
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869790"
---
# <a name="order-by-clause-visual-basic"></a>Предложение Order By (Visual Basic)

Задает порядок сортировки для результата запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Компоненты  

 `orderExp1`  
 Обязательный элемент. Одно или несколько полей из текущего результата запроса, которые указывают порядок упорядочения возвращаемых значений. Имена полей должны быть разделены запятыми (,). Каждое поле можно задать как отсортированное в порядке возрастания или убывания с помощью `Ascending` `Descending` ключевых слов или. Если `Ascending` `Descending` ключевое слово or не указано, используется порядок сортировки по возрастанию. Поля порядка сортировки получают приоритет слева направо.  
  
## <a name="remarks"></a>Remarks  

 `Order By`Для сортировки результатов запроса можно использовать предложение. `Order By`Предложение может сортировать результат только на основе переменной диапазона для текущей области. Например, `Select` предложение вводит новую область в выражении запроса с новыми переменными итерации для этой области. Переменные диапазона, определенные перед `Select` предложением в запросе, недоступны после `Select` предложения. Поэтому, если требуется упорядочить результаты по полю, которое недоступно в `Select` предложении, необходимо поместить `Order By` предложение перед `Select` предложением. Одним из примеров того, когда это потребуется, является то, что нужно отсортировать запрос по полям, которые не возвращаются как часть результата.  
  
 Порядок сортировки для поля по возрастанию и убыванию определяется реализацией <xref:System.IComparable> интерфейса для типа данных поля. Если тип данных не реализует <xref:System.IComparable> интерфейс, порядок сортировки игнорируется.  
  
## <a name="example"></a>Пример  

 Следующее выражение запроса использует `From` предложение для объявления переменной диапазона `book` для `books` коллекции. `Order By`Предложение сортирует результат запроса по цене в возрастающем порядке (по умолчанию). Книги с одинаковой ценой сортируются по названию в возрастающем порядке. `Select`Предложение выбирает `Title` Свойства и в `Price` качестве значений, возвращаемых запросом.  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a>Пример  

 Следующее выражение запроса использует `Order By` предложение для сортировки результата запроса по цене в убывающем порядке. Книги с одинаковой ценой сортируются по названию в возрастающем порядке.  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a>Пример  

 Следующее выражение запроса использует `Select` предложение для выбора названия книги, цены, даты публикации и автора. Затем он заполняет `Title` `Price` поля,, `PublishDate` и `Author` переменной диапазона для новой области. `Order By`Предложение упорядочивает новую переменную диапазона по имени автора, названию книги и стоимости. Каждый столбец сортируется в порядке по умолчанию (по возрастанию).  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
