---
description: Дополнительные сведения о том, как повторно использовать соединение между командой ADO.NET и DataContext.
title: Практическое руководство. Как повторно использовать соединение между командой ADO.NET и DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: d5bf45dfd705ed6e9b9d4ed9659e01bfcb539df2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785956"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Практическое руководство. Как повторно использовать соединение между командой ADO.NET и DataContext

Поскольку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] компонент является частью семейства технологий ADO.NET и основан на службах, предоставляемых ADO.NET, можно повторно использовать подключение между командой ADO.NET и <xref:System.Data.Linq.DataContext> .  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как повторно использовать то же подключение между командой ADO.NET и <xref:System.Data.Linq.DataContext> .  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Основные сведения](background-information.md)
- [ADO.NET и LINQ to SQL](ado-net-and-linq-to-sql.md)
- [Установка связи с базой данных](communicating-with-the-database.md)
