---
title: '!= (не равно) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: bebe85072f5a2cf6a133b88c6d3f5c97299aa63f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191779"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="48233-102">!= (не равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="48233-102">!= (Not Equal To) (Entity SQL)</span></span>

<span data-ttu-id="48233-103">Сравнивает два выражения, чтобы определить, является ли значение левого выражения не равным значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="48233-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="48233-104">Действие оператора != (не равно) эквивалентно действию оператора <>.</span><span class="sxs-lookup"><span data-stu-id="48233-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48233-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48233-105">Syntax</span></span>  
  
```sql  
expression != expression  
-- or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="48233-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="48233-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="48233-107">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="48233-107">Any valid expression.</span></span> <span data-ttu-id="48233-108">Оба выражения должны иметь типы данных, допускающие неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="48233-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="48233-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="48233-109">Result Types</span></span>  

 <span data-ttu-id="48233-110">`true` , если значение левого выражения не равно значению правого; в противном случае - `false`.</span><span class="sxs-lookup"><span data-stu-id="48233-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48233-111">Пример</span><span class="sxs-lookup"><span data-stu-id="48233-111">Example</span></span>  

 <span data-ttu-id="48233-112">В следующем запросе Entity SQL оператор != используется для сравнения двух выражений, чтобы определить, отличается ли значение левого выражения от значения правого.</span><span class="sxs-lookup"><span data-stu-id="48233-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="48233-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="48233-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="48233-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="48233-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="48233-115">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="48233-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="48233-116">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="48233-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="48233-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48233-117">See also</span></span>

- [<span data-ttu-id="48233-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="48233-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
