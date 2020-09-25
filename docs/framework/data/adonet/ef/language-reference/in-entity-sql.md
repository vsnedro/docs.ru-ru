---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 582a3b988247f1484197c0905fecf7f4407f88b0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203674"
---
# <a name="in-entity-sql"></a>IN (Entity SQL)

Определяет, совпадает ли значение с каким-либо значением в коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `value`  
 Любое допустимое выражение, возвращающее значение для сопоставления.  
  
 [ NOT ]  
 Указывает, что значение `Boolean` оператора IN следует инвертировать.  
  
 `expression`  
 Любое допустимое выражение, возвращающее коллекцию для проверки соответствия. Все выражения должны иметь тот же тип, что и аргумент `value`, или принадлежать к базовому или производному типу для типа этого аргумента.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Значение `true`, если значение найдено в коллекции. Значение NULL, если параметр value имеет значение NULL или коллекция пуста. В противном случае - значение `false`. Использование NOT IN логически инвертирует результат IN.  
  
## <a name="example"></a>Пример  

 В следующем запросе на языке Entity SQL оператор IN используется для определения, совпадает ли значение с каким-либо значением в коллекции. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
