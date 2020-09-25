---
title: '- Вычесть (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 17841f336ed186dcbc50b84254048546b15297e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181041"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="ada2b-102">- (вычитание) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ada2b-102">- (Subtract) (Entity SQL)</span></span>

<span data-ttu-id="ada2b-103">Выполняет вычитание двух чисел.</span><span class="sxs-lookup"><span data-stu-id="ada2b-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ada2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ada2b-104">Syntax</span></span>  
  
```sql  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ada2b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ada2b-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="ada2b-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="ada2b-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ada2b-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="ada2b-107">Result Types</span></span>  

 <span data-ttu-id="ada2b-108">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="ada2b-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="ada2b-109">Дополнительные сведения о неявном повышении типа см. в разделе [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ada2b-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ada2b-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ada2b-110">Example</span></span>  

 <span data-ttu-id="ada2b-111">Следующий запрос Entity SQL использует арифметический оператор вычитания (-) для вычитания одного числа из другого.</span><span class="sxs-lookup"><span data-stu-id="ada2b-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="ada2b-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ada2b-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ada2b-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="ada2b-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ada2b-114">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ada2b-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ada2b-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ada2b-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SUBTRACT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="ada2b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ada2b-116">See also</span></span>

- [<span data-ttu-id="ada2b-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ada2b-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
