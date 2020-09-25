---
title: Практическое руководство. Как отобразить набор изменений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: 288920567db75dc1d4c7273f698467063af52ed6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180781"
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="7527e-102">Практическое руководство. Как отобразить набор изменений</span><span class="sxs-lookup"><span data-stu-id="7527e-102">How to: Display a ChangeSet</span></span>

<span data-ttu-id="7527e-103">Для просмотра изменений, отслеживаемых <xref:System.Data.Linq.DataContext>, можно воспользоваться методом <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span><span class="sxs-lookup"><span data-stu-id="7527e-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7527e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7527e-104">Example</span></span>  

 <span data-ttu-id="7527e-105">В следующем примере извлекаются клиенты, находящиеся в Лондоне, город меняется на Париж, а изменения передаются назад в базу данных.</span><span class="sxs-lookup"><span data-stu-id="7527e-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="7527e-106">Этот код выводит следующий результат.</span><span class="sxs-lookup"><span data-stu-id="7527e-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="7527e-107">Обратите внимание, что в итоговой строке в конце указывается число внесенных изменений: 8.</span><span class="sxs-lookup"><span data-stu-id="7527e-107">Note that the summary at the end shows that eight changes were made.</span></span>  

 ```console
CustomerID: AROUT
   Original value: London
   Updated value: Paris
CustomerID: BSBEV
   Original value: London
   Updated value: Paris
CustomerID: CONSH
   Original value: London
   Updated value: Paris
CustomerID: EASTC
   Original value: London
   Updated value: Paris
CustomerID: NORTS
    Original value: London
    Updated value: Paris
CustomerID: PARIS
    Original value: London
    Updated value: Paris
CustomerID: SEVES
    Original value: London
    Updated value: Paris
CustomerID: SPECD
    Original value: London
    Updated value: Paris
Total changes: {Added: 0, Removed: 0, Modified: 8}
```
  
## <a name="see-also"></a><span data-ttu-id="7527e-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7527e-108">See also</span></span>

- [<span data-ttu-id="7527e-109">Поддержка отладки</span><span class="sxs-lookup"><span data-stu-id="7527e-109">Debugging Support</span></span>](debugging-support.md)
