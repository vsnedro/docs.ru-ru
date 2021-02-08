---
description: 'Дополнительные сведения о переменных: Variables (Entity SQL)'
title: Переменные (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 134fee8f61c8e87a18520e6622f6a6a5cceb0076
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795044"
---
# <a name="variables-entity-sql"></a>Переменные (Entity SQL)

## <a name="variable"></a>Переменная  

 Выражение переменной – это ссылка на именованное выражение, определенное в текущей области. Ссылка на переменную должна быть допустимым [!INCLUDE[esql](../../../../../../includes/esql-md.md)] идентификатором, как определено в [идентификаторах](identifiers-entity-sql.md).  
  
 В следующем примере показано применение переменной в выражении. Символ `c` в предложении FROM является определением переменной. Использование символа `c` в предложении SELECT представляет ссылку на переменную.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>См. также

- [Идентификаторы](identifiers-entity-sql.md)
- [Параметры](parameters-entity-sql.md)
- [Общие сведения об Entity SQL](entity-sql-overview.md)
