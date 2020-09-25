---
title: Практическое руководство. Как отключить отложенную загрузку
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: b2193e7e8bda396451274d2da96e7cb86774fd03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196966"
---
# <a name="how-to-turn-off-deferred-loading"></a>Практическое руководство. Как отключить отложенную загрузку

Чтобы отключить отложенную загрузку, свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> следует задать значение `false`. Дополнительные сведения см. в разделе [Отложенная и немедленная загрузка](deferred-versus-immediate-loading.md).  
  
> [!NOTE]
> Отложенная загрузка отключается при отключении отслеживания объекта. Дополнительные сведения см. [в разделе как получить данные только для чтения](how-to-retrieve-information-as-read-only.md).  
  
## <a name="example"></a>Пример  

 В следующем примере показано отключение отложенной загрузки путем установки свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> значения `false`.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- [Основные принципы запросов](query-concepts.md)
- [Запрос к базе данных](querying-the-database.md)
