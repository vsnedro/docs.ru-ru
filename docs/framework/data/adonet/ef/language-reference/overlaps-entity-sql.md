---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: 6902a44af343c37ccb26412738d9f96b28551814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204428"
---
# <a name="overlaps-entity-sql"></a>OVERLAPS (Entity SQL)

Определяет, содержат ли две коллекции общие элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса. Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `true` , если две коллекции содержат общие элементы; в противном случае `false`.  
  
## <a name="remarks"></a>Remarks  

 Перекрытия обеспечивают функционально эквивалент следующего:  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 Оператор OVERLAPS - это один из операторов работы с наборами в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о приоритетах для [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов набора см. в разделе [except](except-entity-sql.md).  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL оператор OVERLAPS используется для определения, имеют ли две коллекции общее значение. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
