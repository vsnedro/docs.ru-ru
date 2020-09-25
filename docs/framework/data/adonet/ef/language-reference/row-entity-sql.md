---
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: 2ab91d0c6d3c3ed3f88a7f0ddbf3a6c2f36d8b04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202262"
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
  
## <a name="see-also"></a>См. также раздел

- [Сборка типов](constructing-types-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
- [Определения типов](type-definitions-entity-sql.md)
