---
description: Дополнительные сведения:! = (не равно) (Entity SQL)
title: '!= (не равно) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: a7a96606fb1834b757253948c3a0d2cde11893dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696403"
---
# <a name="-not-equal-to-entity-sql"></a>!= (не равно) (Entity SQL)

Сравнивает два выражения, чтобы определить, является ли значение левого выражения не равным значению правого выражения. Действие оператора != (не равно) эквивалентно действию оператора <>.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression != expression  
-- or  
expression <> expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающие неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  

 `true` , если значение левого выражения не равно значению правого; в противном случае - `false`.  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL оператор != используется для сравнения двух выражений, чтобы определить, отличается ли значение левого выражения от значения правого. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NOT_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not_equals)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
