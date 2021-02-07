---
description: 'Дополнительные сведения о: HAVING (Entity SQL)'
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 70ace20d67e93aa051873d2b32a49f560902e63d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696884"
---
# <a name="having-entity-sql"></a>HAVING (Entity SQL)

Определяет условие поиска для группы или статистического выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a>Аргументы  

 `search_condition`  
 Определяет условие поиска, которому должна соответствовать группа или статистическое выражение. Если предложение HAVING используется в сочетании с GROUP BY ALL, то оно переопределяет ALL.  
  
## <a name="remarks"></a>Remarks  

 Предложение HAVING позволяет указать дополнительное условие фильтрации для результатов группирования. Если в выражении запроса не указано предложение GROUP BY, то предполагается неявным образом созданная группа, состоящая из одного набора.  
  
> [!NOTE]
> HAVING можно использовать только с инструкцией [SELECT](select-entity-sql.md) . Если [Group By](group-by-entity-sql.md) не используется, то ведет себя как предложение WHERE.  
  
Предложение HAVING работает точно так же, как и предложение WHERE, за исключением того, что применяется после операции GROUP BY. Это означает, что предложение HAVING может создавать ссылки только на псевдонимы и агрегаты группирования, как показано в следующем примере:
  
```sql  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 Предыдущий пример производится ограничение до тех групп, которые содержат более одного товара.  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL операторы HAVING и GROUP BY задают условие поиска для группы или статистического выражения. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#HAVING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#having)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Выражения запросов](query-expressions-entity-sql.md)
