---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 217cd9b2a428c890d83d2b55d45321a04488398e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203648"
---
# <a name="intersect-entity-sql"></a>INTERSECT (Entity SQL)

Возвращает коллекцию различных значений, возвращаемых выражениями запроса, указанных как слева, так и справа от операнда INTERSECT. Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Коллекция того же типа, что и параметр `expression`, или же базового или производного типа для типа этого параметра.  
  
## <a name="remarks"></a>Remarks  

 INTERSECT - один из операторов для работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о приоритетах для [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов набора см. в разделе [except](except-entity-sql.md).  
  
## <a name="example"></a>Пример  

 Следующий запрос Entity SQL использует оператор INTERSECT, чтобы вернуть коллекцию различных значений, возвращаемых выражениями запроса, указанных как слева, так и справа от операнда INTERSECT. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
