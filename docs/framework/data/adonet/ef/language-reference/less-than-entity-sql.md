---
title: < (меньше) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 389c50a697c90dadb075369fe696f7382caf3cff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161923"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="40b71-102">\< (меньше) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="40b71-102">\< (Less Than) (Entity SQL)</span></span>

<span data-ttu-id="40b71-103">Сравнивает два выражения, чтобы определить, является ли значение левого выражения меньшим, чем значение правого выражения.</span><span class="sxs-lookup"><span data-stu-id="40b71-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b71-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40b71-104">Syntax</span></span>  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="40b71-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="40b71-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="40b71-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="40b71-106">Any valid expression.</span></span> <span data-ttu-id="40b71-107">Оба выражения должны иметь типы данных, допускающие неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="40b71-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="40b71-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="40b71-108">Result Types</span></span>  

 <span data-ttu-id="40b71-109">`true` , если значение левого выражения меньше, чем правого; в противном случае - `false`.</span><span class="sxs-lookup"><span data-stu-id="40b71-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40b71-110">Пример</span><span class="sxs-lookup"><span data-stu-id="40b71-110">Example</span></span>  

 <span data-ttu-id="40b71-111">В следующем запросе Entity SQL оператор < используется для сравнения двух выражений, чтобы определить, является ли значение левого выражения меньшим, чем правого.</span><span class="sxs-lookup"><span data-stu-id="40b71-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="40b71-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="40b71-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="40b71-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="40b71-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="40b71-114">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="40b71-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="40b71-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="40b71-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="40b71-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="40b71-116">See also</span></span>

- [<span data-ttu-id="40b71-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="40b71-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
