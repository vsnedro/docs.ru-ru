---
description: Дополнительные сведения о том, как заключать отправку данных с помощью транзакций.
title: Практическое руководство. Как объединить в пакеты отправку данных с помощью транзакций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: a1bbebfcdb4b65e83c4ac6dc9b87b06f33f2cb41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739031"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Практическое руководство. Как объединить в пакеты отправку данных с помощью транзакций

Для объединения запросов к базе данных в брекеты можно использовать класс <xref:System.Transactions.TransactionScope>. Дополнительные сведения см. в разделе [Поддержка транзакций](transaction-support.md).  
  
## <a name="example"></a>Пример  

 В следующем коде отправка данных помещается в класс <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Загрузка примеров баз данных](downloading-sample-databases.md)
- [Внесение и отправка изменений данных](making-and-submitting-data-changes.md)
- [Поддержка транзакций](transaction-support.md)
