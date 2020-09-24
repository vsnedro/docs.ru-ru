---
title: '- Деление (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: d7d25d8c5b91850b21e36ba8f6f668af7a7d0045
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148165"
---
# <a name="-divide-entity-sql"></a>/ (деление) (Entity SQL)

делит одно число на другое.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a>Аргументы  

 `dividend`  
 Делимое числовое выражение. `dividend` - любое допустимое выражение с любым числовым типом данных.  
  
 `divisor`  
 Числовое выражение, на которое делится делимое. `divisor` - любое допустимое выражение с любым числовым типом данных.  
  
## <a name="result-types"></a>Типы результата  

 Тип данных, который является результатом неявного повышения типов обоих аргументов. Дополнительные сведения о неявном повышении типа см. в разделе [System Type](type-system-entity-sql.md).  
  
## <a name="example"></a>Пример  

 Следующий Entity SQL запрос использует арифметический оператор/для деления одного числа на другое. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
