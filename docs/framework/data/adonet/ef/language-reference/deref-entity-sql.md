---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: c0c975ab5cf2761496db6efa1f88f409aa1b1abd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148221"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="cbacf-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cbacf-102">DEREF (Entity SQL)</span></span>

<span data-ttu-id="cbacf-103">Разыменовывает значение ссылки и выдает результат разыменования.</span><span class="sxs-lookup"><span data-stu-id="cbacf-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbacf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbacf-104">Syntax</span></span>  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a><span data-ttu-id="cbacf-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cbacf-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="cbacf-106">Любое допустимое выражение запроса, возвращающее коллекцию.</span><span class="sxs-lookup"><span data-stu-id="cbacf-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbacf-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cbacf-107">Return Value</span></span>  

 <span data-ttu-id="cbacf-108">Значение сущности, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="cbacf-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbacf-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbacf-109">Remarks</span></span>  

 <span data-ttu-id="cbacf-110">Оператор DEREF разыменовывает значение ссылки и выдает результат разыменования.</span><span class="sxs-lookup"><span data-stu-id="cbacf-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="cbacf-111">Например, если `r` является ссылкой на тип ref \<T> , `Deref(r)` то является выражением типа `T` , который возвращает сущность, на которую ссылается `r` .</span><span class="sxs-lookup"><span data-stu-id="cbacf-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="cbacf-112">Если ссылка имеет значение null или висячее значение (т. е. цель ссылки не существует), то результатом оператора DEREF будет значение null.</span><span class="sxs-lookup"><span data-stu-id="cbacf-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbacf-113">Пример</span><span class="sxs-lookup"><span data-stu-id="cbacf-113">Example</span></span>  

 <span data-ttu-id="cbacf-114">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор DEREF используется для разыменования значения ссылки и возврата результата разыменования.</span><span class="sxs-lookup"><span data-stu-id="cbacf-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="cbacf-115">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="cbacf-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cbacf-116">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="cbacf-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cbacf-117">Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cbacf-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="cbacf-118">Передайте методу ExecutePrimitiveTypeQuery следующий запрос в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="cbacf-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="cbacf-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cbacf-119">See also</span></span>

- [<span data-ttu-id="cbacf-120">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cbacf-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="cbacf-121">ЗНАЧ</span><span class="sxs-lookup"><span data-stu-id="cbacf-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="cbacf-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="cbacf-122">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="cbacf-123">KEY</span><span class="sxs-lookup"><span data-stu-id="cbacf-123">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="cbacf-124">Допускающие значения NULL структурированные типы</span><span class="sxs-lookup"><span data-stu-id="cbacf-124">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
