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
# <a name="query-expressions-entity-sql"></a><span data-ttu-id="2c714-102">Выражения запросов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2c714-102">Query Expressions (Entity SQL)</span></span>

<span data-ttu-id="2c714-103">Выражение запроса объединяет в едином синтаксисе множество разных операторов запросов.</span><span class="sxs-lookup"><span data-stu-id="2c714-103">A query expression combines many different query operators into a single syntax.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="2c714-104">предоставляет различные типы выражений, включая [литералы](literals-entity-sql.md), [Параметры](parameters-entity-sql.md), [переменные](variables-entity-sql.md), операторы, [функции](functions-entity-sql.md), операторы SET и т. д.</span><span class="sxs-lookup"><span data-stu-id="2c714-104">provides various kinds of expressions, including the following: [literals](literals-entity-sql.md), [parameters](parameters-entity-sql.md), [variables](variables-entity-sql.md), operators, [functions](functions-entity-sql.md), set operators, and so on.</span></span> <span data-ttu-id="2c714-105">Дополнительные сведения см. в разделе [Справочник по Entity SQL](entity-sql-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2c714-105">For more information, see [Entity SQL Reference](entity-sql-reference.md).</span></span>  
  
## <a name="clauses"></a><span data-ttu-id="2c714-106">Предложения</span><span class="sxs-lookup"><span data-stu-id="2c714-106">Clauses</span></span>  

 <span data-ttu-id="2c714-107">Выражение запроса состоит из предложений, которые последовательно применяют операции к набору объектов.</span><span class="sxs-lookup"><span data-stu-id="2c714-107">A query expression is composed of a series of clauses that apply successive operations to a collection of objects.</span></span> <span data-ttu-id="2c714-108">Они основаны на тех же предложениях, которые находятся в стандартной инструкции SQL SELECT: [SELECT](select-entity-sql.md), [from](from-entity-sql.md), [WHERE](where-entity-sql.md), [Group By](group-by-entity-sql.md), [HAVING](having-entity-sql.md)и [ORDER BY](order-by-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2c714-108">They are based on the same clauses found in standard a SQL select statement: [SELECT](select-entity-sql.md), [FROM](from-entity-sql.md), [WHERE](where-entity-sql.md), [GROUP BY](group-by-entity-sql.md), [HAVING](having-entity-sql.md), and [ORDER BY](order-by-entity-sql.md).</span></span>  
  
## <a name="scope"></a><span data-ttu-id="2c714-109">Область</span><span class="sxs-lookup"><span data-stu-id="2c714-109">Scope</span></span>  

 <span data-ttu-id="2c714-110">Имена, определенные в предложении FROM, появляются в области FROM в порядке перечисления, слева направо.</span><span class="sxs-lookup"><span data-stu-id="2c714-110">Names defined in the FROM clause are introduced into the FROM scope in order of appearance, left to right.</span></span> <span data-ttu-id="2c714-111">В списке JOIN выражения могут ссылаться на имена, которые определены в списке ранее.</span><span class="sxs-lookup"><span data-stu-id="2c714-111">In the JOIN list, expressions can refer to names defined earlier in the list.</span></span> <span data-ttu-id="2c714-112">Открытые свойства элементов, указанные в предложении FROM, не добавляются в область FROM. На них всегда следует ссылаться через имя с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="2c714-112">Public properties of elements identified in the FROM clause are not added to the FROM scope: They must be always referenced through the alias-qualified name.</span></span> <span data-ttu-id="2c714-113">Но обычно все части выражения выбора находятся в области FROM.</span><span class="sxs-lookup"><span data-stu-id="2c714-113">Normally, all parts of the select expression are considered within the FROM scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c714-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2c714-114">See also</span></span>

- [<span data-ttu-id="2c714-115">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2c714-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
