---
title: -- (комментарий) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 9ad6e38726d0802c3bc2090a4e6f11f008828ee5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197902"
---
# <a name="---comment-entity-sql"></a>-- (комментарий) (Entity SQL)

Запросы[!INCLUDE[esql](../../../../../../includes/esql-md.md)] могут содержать комментарии. Строка комментария начинается с двух дефисов (`--`).  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a>Аргументы  

 `text_of_comment`  
 Строка, содержащая текст комментария.  
  
## <a name="example"></a>Пример  

 Следующий запрос Entity SQL демонстрирует использование комментариев. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об Entity SQL](entity-sql-overview.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
