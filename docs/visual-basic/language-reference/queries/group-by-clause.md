---
title: Предложение Group By
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: b60f6759ada845d8eab048bceb1e47f9546ee7d0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869953"
---
# <a name="group-by-clause-visual-basic"></a>Предложение Group By (Visual Basic)

Группирует элементы результата запроса. Может также использоваться для применения агрегатных функций к каждой группе. Операция группирования основана на одном или нескольких ключах.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a>Компоненты  
  
- `listField1`, `listField2`  
  
     Необязательный элемент. Одно или несколько полей переменной или переменных запроса, которые явно определяют поля для включения в сгруппированный результат. Если поля не указаны, в сгруппированный результат включаются все поля из переменной или переменных запроса.  
  
- `keyExp1`  
  
     Обязательный элемент. Выражение, которое определяет ключ, используемый для определения групп элементов. Вы можете указать несколько ключей, чтобы задать составной ключ.  
  
- `keyExp2`  
  
     Необязательный элемент. Один или несколько дополнительных ключей, которые объединяются с `keyExp1` для создания составного ключа.  
  
- `aggregateList`  
  
     Обязательный элемент. Одно или несколько выражений, определяющих способ агрегирования групп. Чтобы определить имя элемента для результатов группирования, используйте ключевое слово `Group` , которое может быть в одной из следующих форм:  
  
    ```vb  
    Into Group  
    ```  
  
     -или-  
  
    ```vb  
    Into <alias> = Group  
    ```  
  
     Вы также можете включать агрегатные функции для применения к группе.  
  
## <a name="remarks"></a>Remarks  

 Чтобы разбить результат ы запроса на группы, можно использовать предложение `Group By` . Группирование основывается на ключе или составном ключе, состоящем из нескольких ключей. Элементы, связанные с соответствующими значениями ключа, включаются в одну и ту же группу.  
  
 Чтобы определить имя элемента, используемое для ссылки на группу, применяется параметр `aggregateList` предложения `Into` и ключевое слово `Group` . Вы также можете включать в предложение `Into` агрегатные функции, чтобы вычислять значения для сгруппированных элементов. Список стандартных агрегатных функций см. в разделе [Aggregate Clause](aggregate-clause.md).  
  
## <a name="example"></a>Пример  

 Следующий пример кода группирует список клиентов по их расположению (стране или региону) и предоставляет количество клиентов в каждой группе. Результаты упорядочиваются по названию страны или региона. Результаты группирования упорядочиваются по названию города.  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
- [Предложение ORDER BY](order-by-clause.md)
- [Aggregate Clause](aggregate-clause.md)
- [Предложение Group Join](group-join-clause.md)
