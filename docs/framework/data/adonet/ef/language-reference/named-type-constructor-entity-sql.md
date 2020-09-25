---
title: Конструктор именованных типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: c673b58ee5811e3d3b74b3744d3f5291888e2253
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197785"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="b780c-102">Конструктор именованных типов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b780c-102">Named Type Constructor (Entity SQL)</span></span>

<span data-ttu-id="b780c-103">Используется для создания экземпляров номинальных типов концептуальной модели, например сложных типов или типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="b780c-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b780c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b780c-104">Syntax</span></span>  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b780c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b780c-105">Arguments</span></span>  

 `identifier`  
 <span data-ttu-id="b780c-106">Значение, представляющее собой простой или заключенный в кавычки идентификатор.</span><span class="sxs-lookup"><span data-stu-id="b780c-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="b780c-107">Дополнительные сведения см. в разделе [идентификаторы](identifiers-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="b780c-107">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="b780c-108">Атрибуты типа, которые, как предполагается, должны располагаться в таком же порядке, как и в декларации этого типа.</span><span class="sxs-lookup"><span data-stu-id="b780c-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b780c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b780c-109">Return Value</span></span>  

 <span data-ttu-id="b780c-110">Экземпляры именованных сложных типов и типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="b780c-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b780c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="b780c-111">Remarks</span></span>  

 <span data-ttu-id="b780c-112">В следующих примерах показано, как создавать номинальные и сложные типы.</span><span class="sxs-lookup"><span data-stu-id="b780c-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="b780c-113">Приведенное далее выражение создает экземпляр типа `Person` .</span><span class="sxs-lookup"><span data-stu-id="b780c-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="b780c-114">Приведенное далее выражение создает экземпляр сложного типа.</span><span class="sxs-lookup"><span data-stu-id="b780c-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="b780c-115">Приведенное далее выражение создает экземпляр вложенного сложного типа.</span><span class="sxs-lookup"><span data-stu-id="b780c-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="b780c-116">Приведенное далее выражение создает экземпляр сущности с вложенным сложным типом.</span><span class="sxs-lookup"><span data-stu-id="b780c-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="b780c-117">В следующем примере показано, как инициализировать свойство сложного типа значением null:`MyModel.ZipCode(‘98118’, null)`.</span><span class="sxs-lookup"><span data-stu-id="b780c-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="b780c-118">Пример</span><span class="sxs-lookup"><span data-stu-id="b780c-118">Example</span></span>  

 <span data-ttu-id="b780c-119">В следующем запросе Entity SQL конструктор именованного типа используется для создания экземпляра типа концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="b780c-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="b780c-120">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b780c-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b780c-121">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="b780c-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b780c-122">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b780c-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b780c-123">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b780c-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="b780c-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b780c-124">See also</span></span>

- [<span data-ttu-id="b780c-125">Сборка типов</span><span class="sxs-lookup"><span data-stu-id="b780c-125">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="b780c-126">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b780c-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
