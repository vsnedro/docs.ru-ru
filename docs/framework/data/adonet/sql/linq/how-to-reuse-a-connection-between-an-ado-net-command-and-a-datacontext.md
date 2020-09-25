---
title: Практическое руководство. Как повторно использовать соединение между командой ADO.NET и DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 89c9a12399d3d76487d1fdc2bd82aa037c167710
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197356"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Практическое руководство. Как повторно использовать соединение между командой ADO.NET и DataContext

Поскольку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] компонент является частью семейства технологий ADO.NET и основан на службах, предоставляемых ADO.NET, можно повторно использовать подключение между командой ADO.NET и <xref:System.Data.Linq.DataContext> .  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как повторно использовать то же подключение между командой ADO.NET и <xref:System.Data.Linq.DataContext> .  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>См. также раздел

- [Основные сведения](background-information.md)
- [ADO.NET и LINQ to SQL](ado-net-and-linq-to-sql.md)
- [Установка связи с базой данных](communicating-with-the-database.md)
