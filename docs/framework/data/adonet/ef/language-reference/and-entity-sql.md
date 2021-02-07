---
description: 'Дополнительные сведения: &amp; &amp; (и) (Entity SQL)'
title: '&amp;&amp; ПЕРЕТАСКИВАНИ (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 14fc6bc3f58ac78cb9806a7f421db87bbad048ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697183"
---
# <a name="ampamp-and-entity-sql"></a>&amp;&amp; ПЕРЕТАСКИВАНИ (Entity SQL)

Возвращает значение `true` если оба выражения `true`; в противном случае возвращает значение `false` или `NULL`.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
boolean_expression AND boolean_expression
```

or  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `boolean_expression`  
 Любое допустимое выражение, возвращающее значение типа Boolean.  
  
## <a name="remarks"></a>Remarks  

 Два амперсанда (&&) действуют так же, как оператор AND.  
  
 В следующей таблице указаны возможные входные значения и возвращаемые типы.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|FALSE|NULL|  
|`FALSE`|FALSE|FALSE|FALSE|  
|`NULL`|NULL|FALSE|NULL|  
  
## <a name="example"></a>Пример  

 Следующий запрос Entity SQL демонстрирует, как использовать оператор AND. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
