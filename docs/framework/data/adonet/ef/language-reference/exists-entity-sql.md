---
description: 'Дополнительные сведения о: EXISTs (Entity SQL)'
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: c6c5b86616d63b9cc3389365a96c382101463732
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786385"
---
# <a name="exists-entity-sql"></a>EXISTS (Entity SQL)

Определяет, является ли коллекция пустой.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение, возвращающее коллекцию.  
  
 NOT  
 Указывает, что результат оператора EXISTS должен быть инвертирован.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Значение `true`, если коллекция не пуста; в противном случае - значение `false`.  
  
## <a name="remarks"></a>Remarks  

 EXISTS - это один из операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о приоритетах для [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов набора см. в разделе [except](except-entity-sql.md).  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL оператор EXISTS используется, чтобы определить, пуста ли коллекция. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
