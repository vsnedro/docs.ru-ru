---
description: Дополнительные сведения о том, как выполнять команды SQL непосредственно.
title: Практическое руководство. Как прямо выполнять команды SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 9dd53b3582b6099bae51dc008debd8cb3142e386
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786034"
---
# <a name="how-to-directly-execute-sql-commands"></a>Практическое руководство. Как прямо выполнять команды SQL

Если предположить наличие подключения <xref:System.Data.Linq.DataContext>, для выполнения команд, которые не возвращают объекты, можно воспользоваться методом <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>.  
  
## <a name="example"></a>Пример  

 В следующем примере SQL Server увеличивает цену за единицу на 1.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Как прямо выполнять запросы SQL](how-to-directly-execute-sql-queries.md)
- [Установка связи с базой данных](communicating-with-the-database.md)
