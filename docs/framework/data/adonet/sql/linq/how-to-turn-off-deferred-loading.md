---
description: 'Дополнительные сведения: как отключить отложенную загрузку'
title: Практическое руководство. Как отключить отложенную загрузку
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 739c9b0b65eda73d6c504409395eb805b0c02873
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785839"
---
# <a name="how-to-turn-off-deferred-loading"></a>Практическое руководство. Как отключить отложенную загрузку

Чтобы отключить отложенную загрузку, свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> следует задать значение `false`. Дополнительные сведения см. в разделе [Отложенная и немедленная загрузка](deferred-versus-immediate-loading.md).  
  
> [!NOTE]
> Отложенная загрузка отключается при отключении отслеживания объекта. Дополнительные сведения см. [в разделе как получить данные только для чтения](how-to-retrieve-information-as-read-only.md).  
  
## <a name="example"></a>Пример  

 В следующем примере показано отключение отложенной загрузки путем установки свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> значения `false`.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Основные принципы запросов](query-concepts.md)
- [Запрос к базе данных](querying-the-database.md)
