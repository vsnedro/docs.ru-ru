---
title: '- Отрицатель (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 71749dab073fade854c2a494841e3f6b408ebd1d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204415"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="8634e-102">- (отрицательное) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8634e-102">- (Negative) (Entity SQL)</span></span>

<span data-ttu-id="8634e-103">Возвращает значение числового выражения с противоположным знаком.</span><span class="sxs-lookup"><span data-stu-id="8634e-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8634e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8634e-104">Syntax</span></span>  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8634e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8634e-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="8634e-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="8634e-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8634e-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="8634e-107">Result Types</span></span>  

 <span data-ttu-id="8634e-108">Тип данных `expression`.</span><span class="sxs-lookup"><span data-stu-id="8634e-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8634e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8634e-109">Remarks</span></span>  

 <span data-ttu-id="8634e-110">Если аргумент `expression` имеет тип данных без знака, то типом результата становится тип данных со знаком, который в наибольшей степени связан с типом аргумента `expression`.</span><span class="sxs-lookup"><span data-stu-id="8634e-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="8634e-111">Например, если аргумент `expression` имеет тип Byte, то возвращается значение типа Int16.</span><span class="sxs-lookup"><span data-stu-id="8634e-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8634e-112">Пример</span><span class="sxs-lookup"><span data-stu-id="8634e-112">Example</span></span>  

 <span data-ttu-id="8634e-113">В следующем запросе Entity SQL используется арифметический оператор «-» для возврата значения числового выражения с противоположным знаком.</span><span class="sxs-lookup"><span data-stu-id="8634e-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="8634e-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="8634e-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8634e-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="8634e-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8634e-116">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8634e-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8634e-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="8634e-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="8634e-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8634e-118">See also</span></span>

- [<span data-ttu-id="8634e-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8634e-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
