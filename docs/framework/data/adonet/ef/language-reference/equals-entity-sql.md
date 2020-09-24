---
title: = (равно) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 31299670d9f47ed7672b980a3415b8d214463b8e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148091"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="2181d-102">= (равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2181d-102">= (Equals) (Entity SQL)</span></span>

<span data-ttu-id="2181d-103">Проверяет равенство двух выражений.</span><span class="sxs-lookup"><span data-stu-id="2181d-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2181d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2181d-104">Syntax</span></span>  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2181d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2181d-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="2181d-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="2181d-106">Any valid expression.</span></span> <span data-ttu-id="2181d-107">Оба выражения должны иметь типы данных, допускающие неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="2181d-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2181d-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="2181d-108">Result Types</span></span>  

 <span data-ttu-id="2181d-109">Имеет значение`true` , если левое выражение равно правому выражению. В противном случае имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2181d-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2181d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="2181d-110">Remarks</span></span>  

 <span data-ttu-id="2181d-111">Оператор == эквивалентен оператору =.</span><span class="sxs-lookup"><span data-stu-id="2181d-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2181d-112">Пример</span><span class="sxs-lookup"><span data-stu-id="2181d-112">Example</span></span>  

 <span data-ttu-id="2181d-113">В следующем запросе Entity SQL оператор сравнения = используется для сравнения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="2181d-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="2181d-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="2181d-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2181d-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="2181d-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2181d-116">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2181d-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2181d-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2181d-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="2181d-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2181d-118">See also</span></span>

- [<span data-ttu-id="2181d-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2181d-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
