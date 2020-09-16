---
title: Вызов функций в запросах LINQ to Entities
description: Используйте эти статьи, чтобы увидеть, как классы Ентитифунктионс и Склфунктионс предоставляют доступ к каноническим и функциям базы данных в составе Entity Framework.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: eb206e9b331da1ae442c1f310e78fec5c6b57e82
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546052"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="66479-103">Вызов функций в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="66479-103">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="66479-104">В подразделах этого раздела описывается вызов функций в запросах LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="66479-104">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="66479-105">Классы <xref:System.Data.Objects.EntityFunctions> и <xref:System.Data.Objects.SqlClient.SqlFunctions> обеспечивают доступ к каноническим функциям и функциям базы данных посредством платформы Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="66479-105">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="66479-106">Дополнительные сведения см. в статьях [как вызывать канонические функции](how-to-call-canonical-functions.md) и [как вызывать функции базы данных](how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="66479-106">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="66479-107">Процесс вызова пользовательской функции состоит из трех основных шагов.</span><span class="sxs-lookup"><span data-stu-id="66479-107">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="66479-108">Определите функцию в концептуальной модели или объявите функцию в модели хранения.</span><span class="sxs-lookup"><span data-stu-id="66479-108">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="66479-109">Добавьте метод в приложение и сопоставьте его с функцией в модели с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="66479-109">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="66479-110">Вызовите функцию в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="66479-110">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="66479-111">Дополнительные сведения см. в подразделах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="66479-111">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66479-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="66479-112">In This Section</span></span>  
 [<span data-ttu-id="66479-113">Практическое руководство. Вызов канонических функций</span><span class="sxs-lookup"><span data-stu-id="66479-113">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="66479-114">Практическое руководство. Вызов функций базы данных</span><span class="sxs-lookup"><span data-stu-id="66479-114">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="66479-115">Практическое руководство. Вызов настраиваемых функций базы данных</span><span class="sxs-lookup"><span data-stu-id="66479-115">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="66479-116">Практическое руководство. Вызов определенных моделью функций в запросах</span><span class="sxs-lookup"><span data-stu-id="66479-116">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="66479-117">Практическое руководство. Вызов определенных моделью функций как методов объектов</span><span class="sxs-lookup"><span data-stu-id="66479-117">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="66479-118">См. также</span><span class="sxs-lookup"><span data-stu-id="66479-118">See also</span></span>

- [<span data-ttu-id="66479-119">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="66479-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="66479-120">Канонические функции</span><span class="sxs-lookup"><span data-stu-id="66479-120">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="66479-121">[Общие сведения о EDMX-файлах](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="66479-121">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="66479-122">[Как определять настраиваемые функции в концептуальной модели](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="66479-122">[How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
