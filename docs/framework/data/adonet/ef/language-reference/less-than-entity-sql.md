---
description: 'Дополнительные сведения: < (меньше) (Entity SQL)'
title: < (меньше) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 523defa6c19ca43a5827258277bbe3f489b9b8c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748288"
---
# <a name="-less-than-entity-sql"></a>\< (меньше) (Entity SQL)

Сравнивает два выражения, чтобы определить, является ли значение левого выражения меньшим, чем значение правого выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающие неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  

 `true` , если значение левого выражения меньше, чем правого; в противном случае - `false`.  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL оператор < используется для сравнения двух выражений, чтобы определить, является ли значение левого выражения меньшим, чем правого. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
