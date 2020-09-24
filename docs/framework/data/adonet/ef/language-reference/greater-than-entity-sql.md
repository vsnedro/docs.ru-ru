---
title: '>  (больше) (язык Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 52a9f9f645aa51402ceb8cb0a40d2040d1c0802c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147948"
---
# <a name="-greater-than-entity-sql"></a>> (больше) (Entity SQL)

Сравнивает два выражения и определяет, имеет ли левое выражение значение больше значения правого выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression > expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающие неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  

 Значение`true` , если левое выражение больше правого. В противном случае - значение `false`.  
  
## <a name="example"></a>Пример  

 Следующий запрос Entity SQL использует оператор сравнения > для сравнения двух выражений и определяет, имеет ли левое выражение значение, большее значения правого выражения. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#GREATER](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
