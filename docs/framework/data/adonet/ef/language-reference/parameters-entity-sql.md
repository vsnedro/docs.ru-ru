---
title: Параметры (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 759452902461e1a460b69774bb33f92bbd532ed0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177523"
---
# <a name="parameters-entity-sql"></a>Параметры (Entity SQL)

Параметры - это переменные, определенные вне [!INCLUDE[esql](../../../../../../includes/esql-md.md)] обычно через привязку API, используемую базовым языком. Каждый параметр имеет имя и тип. Имена параметров определены в выражениях запросов с символом (@) в качестве префикса. Так они отличаются от имен свойств или других имен, определенных в запросе.  
  
 API-привязки базового языка предоставляет API для параметров привязки.  
  
## <a name="example"></a>Пример  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Общие сведения об Entity SQL](entity-sql-overview.md)
