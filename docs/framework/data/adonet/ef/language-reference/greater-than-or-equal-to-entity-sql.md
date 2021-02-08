---
description: 'Дополнительные сведения: >= (больше или равно) (Entity SQL)'
title: '>= (больше или равно) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: d05685123e3262a2d2ae01553c7c5334a7e53c40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786281"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a>>= (больше или равно) (Entity SQL)

Сравнивает два выражения и определяет, имеет ли левое выражение значение, большее или равное значению правого выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression >= expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающие неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  

 Значение`true` , если левое выражение больше или равно правому. В противном случае - значение `false`.  
  
## <a name="example"></a>Пример  

 Следующий запрос Entity SQL использует оператор сравнения >= для сравнения двух выражений и определяет, имеет ли левое выражение значение, большее или равное значению правого выражения. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#GREATER_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater_or_equals)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
