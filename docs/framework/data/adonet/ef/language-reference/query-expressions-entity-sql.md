---
title: Выражения запросов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: ca6b79b4b3d3326a74780345decf58367596adb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175607"
---
# <a name="query-expressions-entity-sql"></a>Выражения запросов (Entity SQL)

Выражение запроса объединяет в едином синтаксисе множество разных операторов запросов. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет различные типы выражений, включая [литералы](literals-entity-sql.md), [Параметры](parameters-entity-sql.md), [переменные](variables-entity-sql.md), операторы, [функции](functions-entity-sql.md), операторы SET и т. д. Дополнительные сведения см. в разделе [Справочник по Entity SQL](entity-sql-reference.md).  
  
## <a name="clauses"></a>Предложения  

 Выражение запроса состоит из предложений, которые последовательно применяют операции к набору объектов. Они основаны на тех же предложениях, которые находятся в стандартной инструкции SQL SELECT: [SELECT](select-entity-sql.md), [from](from-entity-sql.md), [WHERE](where-entity-sql.md), [Group By](group-by-entity-sql.md), [HAVING](having-entity-sql.md)и [ORDER BY](order-by-entity-sql.md).  
  
## <a name="scope"></a>Область  

 Имена, определенные в предложении FROM, появляются в области FROM в порядке перечисления, слева направо. В списке JOIN выражения могут ссылаться на имена, которые определены в списке ранее. Открытые свойства элементов, указанные в предложении FROM, не добавляются в область FROM. На них всегда следует ссылаться через имя с псевдонимом. Но обычно все части выражения выбора находятся в области FROM.  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
