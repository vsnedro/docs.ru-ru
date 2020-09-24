---
title: Практическое руководство. Как объединить в пакеты отправку данных с помощью транзакций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 4d3efedbf15be55fa7a9ab235f881f1c97758953
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161364"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Практическое руководство. Как объединить в пакеты отправку данных с помощью транзакций

Для объединения запросов к базе данных в брекеты можно использовать класс <xref:System.Transactions.TransactionScope>. Дополнительные сведения см. в разделе [Поддержка транзакций](transaction-support.md).  
  
## <a name="example"></a>Пример  

 В следующем коде отправка данных помещается в класс <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- [Загрузка примеров баз данных](downloading-sample-databases.md)
- [Внесение и отправка изменений данных](making-and-submitting-data-changes.md)
- [Поддержка транзакций](transaction-support.md)
