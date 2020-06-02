---
title: Практическое руководство. Как применять определяемые пользователем возвращающие табличное значение функции
description: Используйте эти примеры, чтобы научиться создавать функции с табличным значением, возвращающие один набор строк. Используйте такую функцию, возвращающую табличное значение, как и таблицу.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: 44866367393e321d7dd2db965e2fad8a2e6b63e9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286330"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="7f1cb-104">Практическое руководство. Как применять определяемые пользователем возвращающие табличное значение функции</span><span class="sxs-lookup"><span data-stu-id="7f1cb-104">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="7f1cb-105">Табличная функция возвращает один набор строк (в отличие от хранимых процедур, которые могут возвращать несколько результирующих форм).</span><span class="sxs-lookup"><span data-stu-id="7f1cb-105">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="7f1cb-106">Поскольку типом возвращаемого значения табличной функции является `Table`, эту функцию можно использовать в SQL там, где будет выполняться работа с таблицей.</span><span class="sxs-lookup"><span data-stu-id="7f1cb-106">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="7f1cb-107">Кроме того, табличную функцию можно считать аналогом таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f1cb-107">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f1cb-108">Пример</span><span class="sxs-lookup"><span data-stu-id="7f1cb-108">Example</span></span>  
 <span data-ttu-id="7f1cb-109">Следующая функция SQL явно указывает возвращаемое значение: `TABLE`.</span><span class="sxs-lookup"><span data-stu-id="7f1cb-109">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="7f1cb-110">Поэтому структура возвращаемого набора строк является неявно определенной.</span><span class="sxs-lookup"><span data-stu-id="7f1cb-110">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```sql
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7f1cb-111">сопоставляет функцию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7f1cb-111">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7f1cb-112">Пример</span><span class="sxs-lookup"><span data-stu-id="7f1cb-112">Example</span></span>  
 <span data-ttu-id="7f1cb-113">В следующем коде SQL показана возможность соединения с таблицей, возвращаемой функцией, и, в противном случае, обработать ее как любую другую таблицу.</span><span class="sxs-lookup"><span data-stu-id="7f1cb-113">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```sql
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="7f1cb-114">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запрос должен быть преобразован следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7f1cb-114">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7f1cb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7f1cb-115">See also</span></span>

- [<span data-ttu-id="7f1cb-116">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="7f1cb-116">User-Defined Functions</span></span>](user-defined-functions.md)
