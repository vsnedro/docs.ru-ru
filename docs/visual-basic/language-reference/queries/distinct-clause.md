---
title: Предложение Distinct
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 5aecffbce036500d294d03a925798d51f1269af6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401398"
---
# <a name="distinct-clause-visual-basic"></a>Предложение Distinct (Visual Basic)
Ограничивают значения текущей переменной диапазона, чтобы исключить дублирующиеся значения в последующих предложениях запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Remarks  
 `Distinct`Для получения списка уникальных элементов можно использовать предложение. `Distinct`Предложение приводит к тому, что запрос пропускает дублирующиеся результаты запроса. `Distinct`Предложение применяется к повторяющимися значениям для всех полей возврата, указанных в `Select` предложении. Если `Select` предложение не указано, `Distinct` предложение применяется к переменной диапазона для запроса, указанного в `From` предложении. Если переменная диапазона не является неизменяемым типом, запрос будет игнорировать только результат запроса, если все элементы типа соответствуют существующему результату запроса.  
  
## <a name="example"></a>Пример  
 Следующее выражение запроса соединяет список клиентов и список заказов клиентов. `Distinct`Предложение включается для возврата списка уникальных имен клиентов и дат заказов.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>См. также раздел

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение FROM](from-clause.md)
- [Предложение SELECT](select-clause.md)
- [Предложение WHERE](where-clause.md)
