---
description: 'Дополнительные сведения: <= (меньше или равно) (Entity SQL)'
title: <= (меньше или равно) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: f720c4ef87cdd0cceea175b1ea70caf5ac6e1deb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748262"
---
# <a name="-less-than-or-equal-to-entity-sql"></a>\<= (меньше или равно) (Entity SQL)

Сравнивает два выражения и определяет, имеет ли левое выражение значение, меньшее или равное значению правого выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression <= expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающие неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  

 Значение`true` , если левое выражение меньше или равно правому выражению. В противном случае - значение `false`.  
  
## <a name="example"></a>Пример  

 Следующий запрос Entity SQL использует оператор сравнения <= для сравнения двух выражений и определяет, имеет ли левое выражение значение, меньшее или равное значению правого выражения. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#LESS_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less_or_equals)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
