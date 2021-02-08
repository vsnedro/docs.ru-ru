---
description: 'Дополнительные сведения: SET (Entity SQL)'
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 80be5b76e654c39776d97413c4ece5a8f3df8d2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768029"
---
# <a name="set-entity-sql"></a>SET (Entity SQL)

Выражение SET используется для преобразования коллекции объектов в набор путем получения новой коллекции, из которой удалены все повторяющиеся элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию.  
  
## <a name="remarks"></a>Remarks  

 Выражение набора `SET(c)` логически эквивалентно следующей инструкции SELECT:  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 Оператор`SET` - это один из операторов работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Дополнительные сведения см. в разделе, [за исключением](except-entity-sql.md) сведений о приоритете для [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов набора.  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL используется выражение SET для преобразования коллекции объектов в набор. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
