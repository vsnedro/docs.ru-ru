---
title: = (равно) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 31299670d9f47ed7672b980a3415b8d214463b8e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148091"
---
# <a name="-equals-entity-sql"></a>= (равно) (Entity SQL)

Проверяет равенство двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающие неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  

 Имеет значение`true` , если левое выражение равно правому выражению. В противном случае имеет значение `false`.  
  
## <a name="remarks"></a>Remarks  

 Оператор == эквивалентен оператору =.  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL оператор сравнения = используется для сравнения двух выражений. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
