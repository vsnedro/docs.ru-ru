---
title: Практическое руководство. Как обнаруживать и разрешать конфликты отправки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 96e96208d9bb28092701164e6cd5943ef81515a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147727"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="a195c-102">Практическое руководство. Как обнаруживать и разрешать конфликты отправки</span><span class="sxs-lookup"><span data-stu-id="a195c-102">How to: Detect and Resolve Conflicting Submissions</span></span>

<span data-ttu-id="a195c-103">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет целый ряд ресурсов для обнаружения и разрешения конфликтов, возникающих при внесении изменений в базу данных несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="a195c-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="a195c-104">Дополнительные сведения см. [в разделе руководство. Управление конфликтами изменений](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="a195c-104">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a195c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a195c-105">Example</span></span>  

 <span data-ttu-id="a195c-106">В следующем примере показан `try` / `catch` блок, который перехватывает <xref:System.Data.Linq.ChangeConflictException> исключение.</span><span class="sxs-lookup"><span data-stu-id="a195c-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="a195c-107">Сведения о сущностях и членах для каждого конфликта отображаются в окне «Консоль».</span><span class="sxs-lookup"><span data-stu-id="a195c-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a195c-108">Для поддержки извлечения этих сведений необходимо включить директиву `using System.Reflection` (`Imports System.Reflection` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a195c-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="a195c-109">Для получения дополнительной информации см. <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="a195c-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a195c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a195c-110">See also</span></span>

- [<span data-ttu-id="a195c-111">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="a195c-111">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="a195c-112">Практическое руководство. Как управлять конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="a195c-112">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
