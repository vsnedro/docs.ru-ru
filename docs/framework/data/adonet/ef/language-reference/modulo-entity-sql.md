---
title: (Остаток от деления) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 25bd34db3a627fa708e1ab9a3f0e237426487bcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175711"
---
# <a name="modulo-entity-sql"></a>(Остаток от деления) (Entity SQL)

Возвращает остаток от деления значения одного выражения на другое.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a>Аргументы  

 `dividend`  
 Делимое числовое выражение. `dividend` - любое допустимое выражение с любым числовым типом данных.  
  
 `divisor`  
 Числовое выражение, на которое делится делимое. `divisor` - любое допустимое выражение с любым числовым типом данных.  
  
## <a name="result-types"></a>Типы результата  

 Edm.Int32  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL используется арифметический оператор % для получения остатка от деления одного выражения на другое. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
