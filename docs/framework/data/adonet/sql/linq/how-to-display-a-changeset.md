---
description: Дополнительные сведения о том, как отобразить набор изменений.
title: Практическое руководство. Как отобразить набор изменений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: e5ff7aebcc74ded1300433a3bf7b280db3a11b28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786021"
---
# <a name="how-to-display-a-changeset"></a>Практическое руководство. Как отобразить набор изменений

Для просмотра изменений, отслеживаемых <xref:System.Data.Linq.DataContext>, можно воспользоваться методом <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.  
  
## <a name="example"></a>Пример  

 В следующем примере извлекаются клиенты, находящиеся в Лондоне, город меняется на Париж, а изменения передаются назад в базу данных.  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 Этот код выводит следующий результат. Обратите внимание, что в итоговой строке в конце указывается число внесенных изменений: 8.  

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
  
## <a name="see-also"></a>См. также

- [Поддержка отладки](debugging-support.md)
