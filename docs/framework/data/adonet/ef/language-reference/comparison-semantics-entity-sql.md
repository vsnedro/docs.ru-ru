---
title: Семантика сравнения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 9a36fcc4476c25d64fed670e857f339fb20043d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197837"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="d3eaa-102">Семантика сравнения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d3eaa-102">Comparison Semantics (Entity SQL)</span></span>

<span data-ttu-id="d3eaa-103">Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d3eaa-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="d3eaa-104">Явное сравнение</span><span class="sxs-lookup"><span data-stu-id="d3eaa-104">Explicit comparison</span></span>  

 <span data-ttu-id="d3eaa-105">Операции сравнения:</span><span class="sxs-lookup"><span data-stu-id="d3eaa-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="d3eaa-106">!=</span><span class="sxs-lookup"><span data-stu-id="d3eaa-106">!=</span></span>  
  
 <span data-ttu-id="d3eaa-107">Операции упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="d3eaa-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="d3eaa-108">Операции допустимости значений NULL:</span><span class="sxs-lookup"><span data-stu-id="d3eaa-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="d3eaa-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="d3eaa-109">IS NULL</span></span>  
  
- <span data-ttu-id="d3eaa-110">IS NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="d3eaa-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="d3eaa-111">Явное отличие</span><span class="sxs-lookup"><span data-stu-id="d3eaa-111">Explicit distinction</span></span>  

 <span data-ttu-id="d3eaa-112">Отличие равенства:</span><span class="sxs-lookup"><span data-stu-id="d3eaa-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="d3eaa-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="d3eaa-113">DISTINCT</span></span>  
  
- <span data-ttu-id="d3eaa-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="d3eaa-114">GROUP BY</span></span>  
  
 <span data-ttu-id="d3eaa-115">Отличие упорядочивания:</span><span class="sxs-lookup"><span data-stu-id="d3eaa-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="d3eaa-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d3eaa-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="d3eaa-117">Неявное отличие</span><span class="sxs-lookup"><span data-stu-id="d3eaa-117">Implicit distinction</span></span>  

 <span data-ttu-id="d3eaa-118">Операция и предикаты для работы с наборами (равенство):</span><span class="sxs-lookup"><span data-stu-id="d3eaa-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="d3eaa-119">UNION</span><span class="sxs-lookup"><span data-stu-id="d3eaa-119">UNION</span></span>  
  
- <span data-ttu-id="d3eaa-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="d3eaa-120">INTERSECT</span></span>  
  
- <span data-ttu-id="d3eaa-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="d3eaa-121">EXCEPT</span></span>  
  
- <span data-ttu-id="d3eaa-122">SET</span><span class="sxs-lookup"><span data-stu-id="d3eaa-122">SET</span></span>  
  
- <span data-ttu-id="d3eaa-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="d3eaa-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="d3eaa-124">Предикаты элементов (равенство):</span><span class="sxs-lookup"><span data-stu-id="d3eaa-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="d3eaa-125">IN</span><span class="sxs-lookup"><span data-stu-id="d3eaa-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="d3eaa-126">Поддерживаемые сочетания</span><span class="sxs-lookup"><span data-stu-id="d3eaa-126">Supported Combinations</span></span>  

 <span data-ttu-id="d3eaa-127">В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="d3eaa-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="d3eaa-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="d3eaa-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-129">**!=**</span></span>|<span data-ttu-id="d3eaa-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="d3eaa-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-131">**DISTINCT**</span></span>|<span data-ttu-id="d3eaa-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-132">**UNION**</span></span><br /><br /> <span data-ttu-id="d3eaa-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="d3eaa-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="d3eaa-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-135">**SET**</span></span><br /><br /> <span data-ttu-id="d3eaa-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-136">**OVERLAPS**</span></span>|<span data-ttu-id="d3eaa-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-137">**IN**</span></span>|<span data-ttu-id="d3eaa-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="d3eaa-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-139">**>   >=**</span></span>|<span data-ttu-id="d3eaa-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-140">**ORDER BY**</span></span>|<span data-ttu-id="d3eaa-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="d3eaa-142">**НЕ РАВНО NULL**</span><span class="sxs-lookup"><span data-stu-id="d3eaa-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="d3eaa-143">Тип сущности</span><span class="sxs-lookup"><span data-stu-id="d3eaa-143">Entity type</span></span>|<span data-ttu-id="d3eaa-144">Ссылка<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="d3eaa-145">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="d3eaa-146">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="d3eaa-147">Все свойства<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="d3eaa-148">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-149">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-150">Ссылка<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="d3eaa-151">Сложный тип</span><span class="sxs-lookup"><span data-stu-id="d3eaa-151">Complex type</span></span>|<span data-ttu-id="d3eaa-152">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-153">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-154">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-155">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-156">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-157">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-158">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d3eaa-159">Строка</span><span class="sxs-lookup"><span data-stu-id="d3eaa-159">Row</span></span>|<span data-ttu-id="d3eaa-160">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="d3eaa-161">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="d3eaa-162">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="d3eaa-163">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-164">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-165">Все свойства<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="d3eaa-166">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d3eaa-167">Тип-примитив</span><span class="sxs-lookup"><span data-stu-id="d3eaa-167">Primitive type</span></span>|<span data-ttu-id="d3eaa-168">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d3eaa-168">Provider-specific</span></span>|<span data-ttu-id="d3eaa-169">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d3eaa-169">Provider-specific</span></span>|<span data-ttu-id="d3eaa-170">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d3eaa-170">Provider-specific</span></span>|<span data-ttu-id="d3eaa-171">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d3eaa-171">Provider-specific</span></span>|<span data-ttu-id="d3eaa-172">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d3eaa-172">Provider-specific</span></span>|<span data-ttu-id="d3eaa-173">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d3eaa-173">Provider-specific</span></span>|<span data-ttu-id="d3eaa-174">Зависит от поставщика</span><span class="sxs-lookup"><span data-stu-id="d3eaa-174">Provider-specific</span></span>|  
|<span data-ttu-id="d3eaa-175">Мультинабор</span><span class="sxs-lookup"><span data-stu-id="d3eaa-175">Multiset</span></span>|<span data-ttu-id="d3eaa-176">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-177">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-178">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-179">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-180">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-181">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-182">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d3eaa-183">Ссылочный</span><span class="sxs-lookup"><span data-stu-id="d3eaa-183">Ref</span></span>|<span data-ttu-id="d3eaa-184">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="d3eaa-185">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="d3eaa-186">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="d3eaa-187">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="d3eaa-188">Ключевое слово throw</span><span class="sxs-lookup"><span data-stu-id="d3eaa-188">Throw</span></span>|<span data-ttu-id="d3eaa-189">Ключевое слово throw</span><span class="sxs-lookup"><span data-stu-id="d3eaa-189">Throw</span></span>|<span data-ttu-id="d3eaa-190">Да<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="d3eaa-191">Взаимосвязь</span><span class="sxs-lookup"><span data-stu-id="d3eaa-191">Association</span></span><br /><br /> <span data-ttu-id="d3eaa-192">тип</span><span class="sxs-lookup"><span data-stu-id="d3eaa-192">type</span></span>|<span data-ttu-id="d3eaa-193">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-194">Ключевое слово throw</span><span class="sxs-lookup"><span data-stu-id="d3eaa-194">Throw</span></span>|<span data-ttu-id="d3eaa-195">Ключевое слово throw</span><span class="sxs-lookup"><span data-stu-id="d3eaa-195">Throw</span></span>|<span data-ttu-id="d3eaa-196">Ключевое слово throw</span><span class="sxs-lookup"><span data-stu-id="d3eaa-196">Throw</span></span>|<span data-ttu-id="d3eaa-197">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-198">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="d3eaa-199">Исключение<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="d3eaa-200"><sup>1</sup> Ссылки на заданные экземпляры типа сущности неявно сравниваются, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d3eaa-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="d3eaa-201">Экземпляр сущности нельзя сравнивать с явной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="d3eaa-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="d3eaa-202">При попытке такого сравнения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="d3eaa-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="d3eaa-203">Например, следующий запрос вызовет исключение:</span><span class="sxs-lookup"><span data-stu-id="d3eaa-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="d3eaa-204"><sup>2</sup> Свойства сложных типов выравниваются перед отправкой в хранилище, поэтому они становятся сравнимыми (при условии, что все их свойства сравнимы).</span><span class="sxs-lookup"><span data-stu-id="d3eaa-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="d3eaa-205">См <sup>. также 4.</sup></span><span class="sxs-lookup"><span data-stu-id="d3eaa-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="d3eaa-206"><sup>3</sup> Среда выполнения Entity Framework обнаруживает неподдерживаемый вариант и создает осмысленное исключение без привлечения поставщика или хранилища.</span><span class="sxs-lookup"><span data-stu-id="d3eaa-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="d3eaa-207"><sup>4</sup> Выполняется попытка сравнить все свойства.</span><span class="sxs-lookup"><span data-stu-id="d3eaa-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="d3eaa-208">Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.</span><span class="sxs-lookup"><span data-stu-id="d3eaa-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="d3eaa-209"><sup>5</sup> Сравниваются все отдельные элементы ссылок (в том числе имя набора сущностей и все ключевые свойства типа сущности).</span><span class="sxs-lookup"><span data-stu-id="d3eaa-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3eaa-210">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d3eaa-210">See also</span></span>

- [<span data-ttu-id="d3eaa-211">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d3eaa-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
