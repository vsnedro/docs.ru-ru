---
title: '! (NOT) (язык Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0eb9be9ed4cbce45a51d15eea68e9fb1a26f0107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191844"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="adbb4-103">!</span><span class="sxs-lookup"><span data-stu-id="adbb4-103">!</span></span> <span data-ttu-id="adbb4-104">(NOT) (язык Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="adbb4-104">(NOT) (Entity SQL)</span></span>

<span data-ttu-id="adbb4-105">Изменяет значение выражения типа `Boolean` на обратное.</span><span class="sxs-lookup"><span data-stu-id="adbb4-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adbb4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adbb4-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="adbb4-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="adbb4-107">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="adbb4-108">Любое допустимое выражение, возвращающее значение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="adbb4-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adbb4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="adbb4-109">Remarks</span></span>  

 <span data-ttu-id="adbb4-110">Восклицательный знак (!) имеет ту же функциональность, что и оператор NOT.</span><span class="sxs-lookup"><span data-stu-id="adbb4-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adbb4-111">Пример</span><span class="sxs-lookup"><span data-stu-id="adbb4-111">Example</span></span>  

 <span data-ttu-id="adbb4-112">Следующий запрос Entity SQL использует оператор NOT, чтобы изменить на обратное выражение типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="adbb4-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="adbb4-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="adbb4-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="adbb4-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="adbb4-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="adbb4-115">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="adbb4-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="adbb4-116">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="adbb4-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="adbb4-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="adbb4-117">See also</span></span>

- [<span data-ttu-id="adbb4-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="adbb4-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
