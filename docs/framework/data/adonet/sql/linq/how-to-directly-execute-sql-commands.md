---
title: Практическое руководство. Как прямо выполнять команды SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 6c72e683c37968ce18717b70ef6d647ca287bd20
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147649"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="4cd5e-102">Практическое руководство. Как прямо выполнять команды SQL</span><span class="sxs-lookup"><span data-stu-id="4cd5e-102">How to: Directly Execute SQL Commands</span></span>

<span data-ttu-id="4cd5e-103">Если предположить наличие подключения <xref:System.Data.Linq.DataContext>, для выполнения команд, которые не возвращают объекты, можно воспользоваться методом <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cd5e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4cd5e-104">Example</span></span>  

 <span data-ttu-id="4cd5e-105">В следующем примере SQL Server увеличивает цену за единицу на 1.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4cd5e-106">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4cd5e-106">See also</span></span>

- [<span data-ttu-id="4cd5e-107">Практическое руководство. Как прямо выполнять запросы SQL</span><span class="sxs-lookup"><span data-stu-id="4cd5e-107">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="4cd5e-108">Установка связи с базой данных</span><span class="sxs-lookup"><span data-stu-id="4cd5e-108">Communicating with the Database</span></span>](communicating-with-the-database.md)
