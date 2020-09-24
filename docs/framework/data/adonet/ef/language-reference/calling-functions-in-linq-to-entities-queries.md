---
title: Вызов функций в запросах LINQ to Entities
description: Используйте эти статьи, чтобы увидеть, как классы Ентитифунктионс и Склфунктионс предоставляют доступ к каноническим и функциям базы данных в составе Entity Framework.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 8c771c93e0c3ed82f3ad550613dd855fd06b6f48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177492"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="de2ce-103">Вызов функций в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="de2ce-103">Calling Functions in LINQ to Entities Queries</span></span>

<span data-ttu-id="de2ce-104">В подразделах этого раздела описывается вызов функций в запросах LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="de2ce-104">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="de2ce-105">Классы <xref:System.Data.Objects.EntityFunctions> и <xref:System.Data.Objects.SqlClient.SqlFunctions> обеспечивают доступ к каноническим функциям и функциям базы данных посредством платформы Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="de2ce-105">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="de2ce-106">Дополнительные сведения см. в статьях [как вызывать канонические функции](how-to-call-canonical-functions.md) и [как вызывать функции базы данных](how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="de2ce-106">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="de2ce-107">Процесс вызова пользовательской функции состоит из трех основных шагов.</span><span class="sxs-lookup"><span data-stu-id="de2ce-107">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="de2ce-108">Определите функцию в концептуальной модели или объявите функцию в модели хранения.</span><span class="sxs-lookup"><span data-stu-id="de2ce-108">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="de2ce-109">Добавьте метод в приложение и сопоставьте его с функцией в модели с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="de2ce-109">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="de2ce-110">Вызовите функцию в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="de2ce-110">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="de2ce-111">Дополнительные сведения см. в подразделах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="de2ce-111">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de2ce-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="de2ce-112">In This Section</span></span>  

 [<span data-ttu-id="de2ce-113">Практическое руководство. Вызов канонических функций</span><span class="sxs-lookup"><span data-stu-id="de2ce-113">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="de2ce-114">Практическое руководство. Вызов функций базы данных</span><span class="sxs-lookup"><span data-stu-id="de2ce-114">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="de2ce-115">Практическое руководство. Вызов настраиваемых функций базы данных</span><span class="sxs-lookup"><span data-stu-id="de2ce-115">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="de2ce-116">Практическое руководство. Вызов определенных моделью функций в запросах</span><span class="sxs-lookup"><span data-stu-id="de2ce-116">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="de2ce-117">Практическое руководство. Вызов определенных моделью функций как методов объектов</span><span class="sxs-lookup"><span data-stu-id="de2ce-117">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="de2ce-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="de2ce-118">See also</span></span>

- [<span data-ttu-id="de2ce-119">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="de2ce-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="de2ce-120">Канонические функции</span><span class="sxs-lookup"><span data-stu-id="de2ce-120">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="de2ce-121">[Общие сведения о EDMX-файлах](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="de2ce-121">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="de2ce-122">[Как определять настраиваемые функции в концептуальной модели](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="de2ce-122">[How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
