---
title: Практическое руководство. Как отключить отложенную загрузку
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: b2193e7e8bda396451274d2da96e7cb86774fd03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196966"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="95f91-102">Практическое руководство. Как отключить отложенную загрузку</span><span class="sxs-lookup"><span data-stu-id="95f91-102">How to: Turn Off Deferred Loading</span></span>

<span data-ttu-id="95f91-103">Чтобы отключить отложенную загрузку, свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> следует задать значение `false`.</span><span class="sxs-lookup"><span data-stu-id="95f91-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="95f91-104">Дополнительные сведения см. в разделе [Отложенная и немедленная загрузка](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="95f91-104">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95f91-105">Отложенная загрузка отключается при отключении отслеживания объекта.</span><span class="sxs-lookup"><span data-stu-id="95f91-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="95f91-106">Дополнительные сведения см. [в разделе как получить данные только для чтения](how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="95f91-106">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="95f91-107">Пример</span><span class="sxs-lookup"><span data-stu-id="95f91-107">Example</span></span>  

 <span data-ttu-id="95f91-108">В следующем примере показано отключение отложенной загрузки путем установки свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> значения `false`.</span><span class="sxs-lookup"><span data-stu-id="95f91-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="95f91-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="95f91-109">See also</span></span>

- [<span data-ttu-id="95f91-110">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="95f91-110">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="95f91-111">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="95f91-111">Querying the Database</span></span>](querying-the-database.md)
