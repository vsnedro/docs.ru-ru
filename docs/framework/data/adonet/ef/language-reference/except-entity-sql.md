---
description: 'Дополнительные сведения о: EXCEPT (Entity SQL)'
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: fd66d8dc6e22a73afbfd27e6eb1fd6c8bb9d3475
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786398"
---
# <a name="except-entity-sql"></a>EXCEPT (Entity SQL)

Возвращает коллекцию различных значений из выражения запроса, расположенного левее операнда EXCEPT, за исключением тех, которые были возвращены выражением запроса, расположенного правее операнда EXCEPT. Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Коллекция того же типа, что и параметр `expression`, или же базового или производного типа для типа этого параметра.  
  
## <a name="remarks"></a>Remarks  

 Оператор EXCEPT - это один из операторов работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Следующая таблица демонстрирует очередность операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .  
  
|Приоритет|Операторы|  
|----------------|---------------|  
|Наивысшая|INTERSECT|  
||UNION<br /><br /> UNION ALL|  
||EXCEPT|  
|Наименьшая|EXISTS<br /><br /> OVERLAPS<br /><br /> FLATTEN<br /><br /> SET|  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL с помощью оператора EXCEPT возвращается коллекция отдельных значений из двух выражений запросов. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
