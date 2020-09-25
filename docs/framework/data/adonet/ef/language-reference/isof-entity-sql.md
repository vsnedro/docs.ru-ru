---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 3cbbc9b6feda1bde104ed2c95d4dca274b090028
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202283"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="8dca9-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8dca9-102">ISOF (Entity SQL)</span></span>

<span data-ttu-id="8dca9-103">Определяет, относится ли тип выражения к указанному типу или одному из его подтипов.</span><span class="sxs-lookup"><span data-stu-id="8dca9-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dca9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8dca9-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="8dca9-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8dca9-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="8dca9-106">Любое допустимое выражение запроса для определения типа.</span><span class="sxs-lookup"><span data-stu-id="8dca9-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="8dca9-107">NOT</span><span class="sxs-lookup"><span data-stu-id="8dca9-107">NOT</span></span>  
 <span data-ttu-id="8dca9-108">Выполняет отрицание результата EDM.Boolean для IS OF.</span><span class="sxs-lookup"><span data-stu-id="8dca9-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="8dca9-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="8dca9-109">ONLY</span></span>  
 <span data-ttu-id="8dca9-110">Указывает, что оператор IS OF возвращает значение `true` только в том случае, если выражение `expression` относится к типу `type`, а не одному из его подтипов.</span><span class="sxs-lookup"><span data-stu-id="8dca9-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="8dca9-111">Тип, по которому проверяется выражение `expression`.</span><span class="sxs-lookup"><span data-stu-id="8dca9-111">The type to test `expression` against.</span></span> <span data-ttu-id="8dca9-112">Для типа должно быть указано пространство имен.</span><span class="sxs-lookup"><span data-stu-id="8dca9-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dca9-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8dca9-113">Return Value</span></span>  

 <span data-ttu-id="8dca9-114">Значение `true`, если выражение `expression` относится к типу T, который является либо базовым типом, либо производным типом от типа `type`. Значение null, если выражение `expression` во время выполнения имеет значение null. В противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8dca9-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dca9-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="8dca9-115">Remarks</span></span>  

 <span data-ttu-id="8dca9-116">Выражения `expression IS NOT OF (type)` и `expression IS NOT OF (ONLY type)` являются синтаксически эквивалентными для `NOT (expression IS OF (type))` и `NOT (expression IS OF (ONLY type))` соответственно.</span><span class="sxs-lookup"><span data-stu-id="8dca9-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="8dca9-117">В следующей таблице показано, каким образом оператор `IS OF` работает с некоторыми стандартными и нестандартными конструкциями.</span><span class="sxs-lookup"><span data-stu-id="8dca9-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="8dca9-118">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="8dca9-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="8dca9-119">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8dca9-119">Pattern</span></span>|<span data-ttu-id="8dca9-120">Поведение</span><span class="sxs-lookup"><span data-stu-id="8dca9-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="8dca9-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="8dca9-122">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="8dca9-122">Throws</span></span>|  
|<span data-ttu-id="8dca9-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="8dca9-124">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="8dca9-124">Throws</span></span>|  
|<span data-ttu-id="8dca9-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-125">null IS OF (RowType)</span></span>|<span data-ttu-id="8dca9-126">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="8dca9-126">Throws</span></span>|  
|<span data-ttu-id="8dca9-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="8dca9-128">Возвращает DBNull</span><span class="sxs-lookup"><span data-stu-id="8dca9-128">Returns DBNull</span></span>|  
|<span data-ttu-id="8dca9-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="8dca9-130">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="8dca9-130">Throws</span></span>|  
|<span data-ttu-id="8dca9-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="8dca9-132">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="8dca9-132">Throws</span></span>|  
|<span data-ttu-id="8dca9-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="8dca9-134">Возвращает значение true или false</span><span class="sxs-lookup"><span data-stu-id="8dca9-134">Returns true/false</span></span>|  
|<span data-ttu-id="8dca9-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="8dca9-136">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="8dca9-136">Throws</span></span>|  
|<span data-ttu-id="8dca9-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="8dca9-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="8dca9-138">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="8dca9-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8dca9-139">Пример</span><span class="sxs-lookup"><span data-stu-id="8dca9-139">Example</span></span>  

 <span data-ttu-id="8dca9-140">В следующем [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запросе используется оператор is of для определения типа выражения запроса, а затем оператор TREAT используется для преобразования объекта курса типа в коллекцию объектов типа OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="8dca9-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="8dca9-141">Запрос основан на [модели School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8dca9-141">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 <span data-ttu-id="8dca9-142">[! code-SQL [DP Ентитисервицес основные понятия # TREAT_ISOF] ~/самплес/сниппетс/тскл/VS_Snippets_Data/DP ентитисервицес основные понятия/TSQL/ентитискл. SQL # treat_isof)]</span><span class="sxs-lookup"><span data-stu-id="8dca9-142">[!code-sql[DP EntityServices Concepts#TREAT_ISOF]~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dca9-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8dca9-143">See also</span></span>

- [<span data-ttu-id="8dca9-144">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8dca9-144">Entity SQL Reference</span></span>](entity-sql-reference.md)
