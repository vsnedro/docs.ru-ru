---
description: Дополнительные сведения:! (NOT) (язык Entity SQL)
title: '! (NOT) (язык Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 648cc4ff73769ae280570b2d42934b2001fa5182
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696455"
---
# <a name="-not-entity-sql"></a>! (NOT) (язык Entity SQL)

Изменяет значение выражения типа `Boolean` на обратное.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a>Аргументы  

 `boolean_expression`  
 Любое допустимое выражение, возвращающее значение типа Boolean.  
  
## <a name="remarks"></a>Remarks  

 Восклицательный знак (!) имеет ту же функциональность, что и оператор NOT.  
  
## <a name="example"></a>Пример  

 Следующий запрос Entity SQL использует оператор NOT, чтобы изменить на обратное выражение типа `Boolean` . Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
