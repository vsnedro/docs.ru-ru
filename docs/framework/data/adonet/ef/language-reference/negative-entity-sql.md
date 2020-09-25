---
title: '- Отрицатель (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 71749dab073fade854c2a494841e3f6b408ebd1d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204415"
---
# <a name="--negative-entity-sql"></a>- (отрицательное) (Entity SQL)

Возвращает значение числового выражения с противоположным знаком.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Любое допустимое выражение с любым числовым типом данных.  
  
## <a name="result-types"></a>Типы результата  

 Тип данных `expression`.  
  
## <a name="remarks"></a>Remarks  

 Если аргумент `expression` имеет тип данных без знака, то типом результата становится тип данных со знаком, который в наибольшей степени связан с типом аргумента `expression`. Например, если аргумент `expression` имеет тип Byte, то возвращается значение типа Int16.  
  
## <a name="example"></a>Пример  

 В следующем запросе Entity SQL используется арифметический оператор «-» для возврата значения числового выражения с противоположным знаком. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
