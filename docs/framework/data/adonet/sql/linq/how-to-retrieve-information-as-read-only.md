---
title: Практическое руководство. Как получать информацию в режиме только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 0a6853ef5d0b67e5efb95731adb5a106e8701e0f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155839"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="2697f-102">Практическое руководство. Как получать информацию в режиме только для чтения</span><span class="sxs-lookup"><span data-stu-id="2697f-102">How to: Retrieve Information As Read-Only</span></span>

<span data-ttu-id="2697f-103">Если не планируется изменять данные, можно повысить производительность запросов за счет поиска результатов, предназначенных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2697f-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="2697f-104">Чтобы реализовать обработку запросов только для чтения, установите для свойства <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2697f-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2697f-105">Если для свойства <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> установлено значение `false`, то для свойства <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> неявно устанавливается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2697f-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2697f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2697f-106">Example</span></span>  

 <span data-ttu-id="2697f-107">В следующем примере кода извлекается коллекция дат приема на работу сотрудников, предназначенная только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2697f-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2697f-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2697f-108">See also</span></span>

- [<span data-ttu-id="2697f-109">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="2697f-109">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="2697f-110">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="2697f-110">Querying the Database</span></span>](querying-the-database.md)
- [<span data-ttu-id="2697f-111">Отложенная и немедленная загрузка</span><span class="sxs-lookup"><span data-stu-id="2697f-111">Deferred versus Immediate Loading</span></span>](deferred-versus-immediate-loading.md)
