---
description: 'Дополнительные сведения: ROW (Entity SQL)'
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: 2d0bcf3c5be8ef3b67e170af5159ae7dd8744630
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739278"
---
# <a name="row-entity-sql"></a>ROW (Entity SQL)

Создает анонимные структурно типизированные записи из одного или нескольких значений.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение запроса, которое возвращает значение для создания в типе строки.  
  
 `alias`  
 Определяет псевдоним для значения, указанного в типе строки. Если псевдоним не указан, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается сформировать его на основе правил создания псевдонимов [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .  
  
## <a name="return-value"></a>Возвращаемое значение  

 Тип строки.  
  
## <a name="remarks"></a>Remarks  

 В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] конструкторы строк можно использовать для создания анонимных структурно типизированных записей из одного или нескольких значений. Итоговый тип конструктора строк является типом строки, типы полей которого соответствуют типам значений, которые использовались для создания этой строки. Например, следующее выражение создает значение типа `Record(a int, b string, c int)`.  
  
```sql  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 Если в конструкторе строк не указан псевдоним для выражения, то платформа Entity Framework попытается сформировать его. Дополнительные сведения см. в разделе «Правила присвоения псевдонимов» темы [Идентификаторы](identifiers-entity-sql.md) .  
  
 В конструкторе строк псевдонимы присваиваются выражениям по следующим правилам.  
  
- Выражение в конструкторе строк не может ссылаться на другие псевдонимы в этом же конструкторе.  
  
- Два выражения в одном конструкторе строк не могут иметь одинаковый псевдоним.  
  
 Дополнительные сведения о конструкторах запросов см. в разделе [Создание типов](constructing-types-entity-sql.md).  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL оператор ROW используется для создания анонимных структурно типизированных записей. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#ROW](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#row)]  
  
## <a name="see-also"></a>См. также

- [Сборка типов](constructing-types-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
- [Определения типов](type-definitions-entity-sql.md)
