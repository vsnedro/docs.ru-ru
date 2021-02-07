---
description: Дополнительные сведения:--(комментарий) (Entity SQL)
title: -- (комментарий) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 793649177d9e64bead7b8755f35bdb51f53f4dd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724977"
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
  
## <a name="see-also"></a>См. также

- [Общие сведения об Entity SQL](entity-sql-overview.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
