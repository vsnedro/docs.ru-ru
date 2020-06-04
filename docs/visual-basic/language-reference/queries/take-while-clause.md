---
title: Предложение Take While
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 4b6133efdbd9c46ab85201ad454671e5538b6a81
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359584"
---
# <a name="take-while-clause-visual-basic"></a>Предложение Take While (Visual Basic)
Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательный. Выражение, представляющее условие для проверки элементов. Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например, `Integer` для вычисления в виде `Boolean` .|  
  
## <a name="remarks"></a>Комментарии  
 `Take While`Предложение включает элементы из начала результата запроса до тех пор, пока не будут `expression` возвращены `false` . После `expression` возврата `false` запрос будет обходить все оставшиеся элементы. `expression`Для оставшихся результатов игнорируется.  
  
 `Take While`Предложение отличается от `Where` предложения в том, что `Where` предложение может использоваться для включения всех элементов из запроса, удовлетворяющего определенному условию. `Take While`Предложение включает элементы только до первого момента, когда условие не будет удовлетворено. `Take While`Предложение наиболее полезно при работе с упорядоченным результатом запроса.  
  
## <a name="example"></a>Пример  
 В следующем примере кода предложение используется `Take While` для получения результатов до тех пор, пока не будет найден первый клиент без заказов.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>См. также раздел

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
- [Предложение Take](take-clause.md)
- [Предложение Skip While](skip-while-clause.md)
- [Предложение WHERE](where-clause.md)
