---
title: + (сложение)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: b86d273658362c3bb204d5220ff5e9db1f8de9fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198058"
---
# <a name="-add"></a><span data-ttu-id="d58ed-102">+ (сложение)</span><span class="sxs-lookup"><span data-stu-id="d58ed-102">+ (Add)</span></span>

<span data-ttu-id="d58ed-103">складывает два числа.</span><span class="sxs-lookup"><span data-stu-id="d58ed-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d58ed-104">Syntax</span></span>  
  
```csharp  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d58ed-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d58ed-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="d58ed-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="d58ed-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d58ed-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="d58ed-107">Result Types</span></span>  

 <span data-ttu-id="d58ed-108">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="d58ed-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="d58ed-109">Дополнительные сведения о неявном повышении типа см. в разделе [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d58ed-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d58ed-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d58ed-110">Remarks</span></span>  

 <span data-ttu-id="d58ed-111">Для типов EDM.String сложение является объединением строк.</span><span class="sxs-lookup"><span data-stu-id="d58ed-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d58ed-112">Пример</span><span class="sxs-lookup"><span data-stu-id="d58ed-112">Example</span></span>  

 <span data-ttu-id="d58ed-113">В следующем запросе Entity SQL арифметический оператор сложения (+) используется для сложения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="d58ed-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="d58ed-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="d58ed-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d58ed-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="d58ed-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d58ed-116">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d58ed-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d58ed-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d58ed-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="d58ed-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d58ed-118">See also</span></span>

- [<span data-ttu-id="d58ed-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d58ed-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="d58ed-120">Типы концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="d58ed-120">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
