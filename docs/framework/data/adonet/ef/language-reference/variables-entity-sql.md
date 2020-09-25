---
title: Переменные (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: af6d586a22f14a04bfc7ec339d0aa8e9ba7c66c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181002"
---
# <a name="variables-entity-sql"></a>Переменные (Entity SQL)

## <a name="variable"></a>Переменная  

 Выражение переменной – это ссылка на именованное выражение, определенное в текущей области. Ссылка на переменную должна быть допустимым [!INCLUDE[esql](../../../../../../includes/esql-md.md)] идентификатором, как определено в [идентификаторах](identifiers-entity-sql.md).  
  
 В следующем примере показано применение переменной в выражении. Символ `c` в предложении FROM является определением переменной. Использование символа `c` в предложении SELECT представляет ссылку на переменную.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>См. также раздел

- [Идентификаторы](identifiers-entity-sql.md)
- [Параметры](parameters-entity-sql.md)
- [Общие сведения об Entity SQL](entity-sql-overview.md)
