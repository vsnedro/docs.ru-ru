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
# <a name="variables-entity-sql"></a><span data-ttu-id="dae1a-102">Переменные (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dae1a-102">Variables (Entity SQL)</span></span>

## <a name="variable"></a><span data-ttu-id="dae1a-103">Переменная</span><span class="sxs-lookup"><span data-stu-id="dae1a-103">Variable</span></span>  

 <span data-ttu-id="dae1a-104">Выражение переменной – это ссылка на именованное выражение, определенное в текущей области.</span><span class="sxs-lookup"><span data-stu-id="dae1a-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="dae1a-105">Ссылка на переменную должна быть допустимым [!INCLUDE[esql](../../../../../../includes/esql-md.md)] идентификатором, как определено в [идентификаторах](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="dae1a-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="dae1a-106">В следующем примере показано применение переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="dae1a-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="dae1a-107">Символ `c` в предложении FROM является определением переменной.</span><span class="sxs-lookup"><span data-stu-id="dae1a-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="dae1a-108">Использование символа `c` в предложении SELECT представляет ссылку на переменную.</span><span class="sxs-lookup"><span data-stu-id="dae1a-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="dae1a-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dae1a-109">See also</span></span>

- [<span data-ttu-id="dae1a-110">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="dae1a-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="dae1a-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="dae1a-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="dae1a-112">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dae1a-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
