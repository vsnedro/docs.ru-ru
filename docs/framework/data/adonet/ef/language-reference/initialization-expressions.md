---
title: Выражения инициализации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 93f590e1c177adf541baca85a48fee5f9eb8d1d0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203635"
---
# <a name="initialization-expressions"></a><span data-ttu-id="52540-102">Выражения инициализации</span><span class="sxs-lookup"><span data-stu-id="52540-102">Initialization Expressions</span></span>

<span data-ttu-id="52540-103">Выражения инициализации инициализируют новый объект.</span><span class="sxs-lookup"><span data-stu-id="52540-103">An initialization expression initializes a new object.</span></span> <span data-ttu-id="52540-104">Поддерживается большинство выражений инициализации, в том числе большинство новых выражений инициализации языков C# 3.0 и Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="52540-104">Most initialization expressions are supported, including most new C# 3.0 and Visual Basic 9.0 initialization expressions.</span></span> <span data-ttu-id="52540-105">Следующие типы могут быть инициализированы и возвращены запросом LINQ to Entities:</span><span class="sxs-lookup"><span data-stu-id="52540-105">The following types can be initialized and returned by a LINQ to Entities query:</span></span>  
  
- <span data-ttu-id="52540-106">Коллекция, которая включает ноль или больше типизированных объектов сущностей, или проекция сложных типов, которая определена в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="52540-106">A collection of zero or more typed entity objects or a projection of complex types that are defined in the conceptual model.</span></span>  
  
- <span data-ttu-id="52540-107">Типы CLR, поддерживаемые Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="52540-107">CLR types supported by the Entity Framework.</span></span>
  
- <span data-ttu-id="52540-108">Встроенные коллекции.</span><span class="sxs-lookup"><span data-stu-id="52540-108">Inline collections.</span></span>  
  
- <span data-ttu-id="52540-109">Анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="52540-109">Anonymous types.</span></span>  
  
 <span data-ttu-id="52540-110">В следующем примере с синтаксисом выражения запроса показана инициализация анонимного типа:</span><span class="sxs-lookup"><span data-stu-id="52540-110">Anonymous type initialization is shown in the following example in query expression syntax:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 <span data-ttu-id="52540-111">Следующий пример с синтаксисом запроса на основе метода показывает инициализацию анонимного типа:</span><span class="sxs-lookup"><span data-stu-id="52540-111">The following example in method-based query syntax shows anonymous type initialization:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 <span data-ttu-id="52540-112">Также поддерживается инициализация определяемого пользователем класса.</span><span class="sxs-lookup"><span data-stu-id="52540-112">User-defined class initialization is also supported.</span></span> <span data-ttu-id="52540-113">Поддерживается модель инициализации языков C# 3.0 и Visual Basic 9.0 и предполагается, что метод считывания и метод задания свойства симметричны.</span><span class="sxs-lookup"><span data-stu-id="52540-113">The C# 3.0 and Visual Basic 9.0 initialization pattern is supported and assumes that the property getter and setter are symmetric.</span></span> <span data-ttu-id="52540-114">В следующем примере синтаксис выражения запроса показывает пользовательский класс, инициализируемый в запросе:</span><span class="sxs-lookup"><span data-stu-id="52540-114">The following example in query expression syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 <span data-ttu-id="52540-115">В следующем примере синтаксис запроса на основе метода показывает пользовательский класс, инициализируемый в запросе:</span><span class="sxs-lookup"><span data-stu-id="52540-115">The following example in method-based query syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="52540-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="52540-116">See also</span></span>

- [<span data-ttu-id="52540-117">Выражения в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="52540-117">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
