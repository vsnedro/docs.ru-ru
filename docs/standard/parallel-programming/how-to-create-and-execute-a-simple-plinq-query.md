---
title: Практическое руководство. Создание и выполнение простого запроса PLINQ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: 67863346046b0c400529b87355c11f97d0c3f01f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827091"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a>Практическое руководство. Создание и выполнение простого запроса PLINQ

В приведенном в этой статье примере показано, как создать простой параллельный запрос LINQ (PLINQ) с помощью метода расширения <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> исходной последовательности, а также выполнить запрос с помощью метода <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
> В этой документации для определения делегатов в PLINQ используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 В данном примере показан базовый шаблон для создания и выполнения любого параллельного запроса LINQ в случае, когда порядок последовательности результатов не имеет значения. Неупорядоченные запросы обычно выполняются быстрее упорядоченных. Запрос делит источник на задачи, выполняемые асинхронно в нескольких потоках. Порядок выполнения каждой из задач зависит не только от объема работы по обработке элементов в разделе, но и от внешних факторов, например, от планирования каждого из потоков операционной системой. Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. См. дополнительные сведения об [ускорении выполнения в PLINQ](understanding-speedup-in-plinq.md). Дополнительные сведения о сохранении порядка элементов в запросе см. в статье [Практическое руководство. Управление порядком в запросе PLINQ](how-to-control-ordering-in-a-plinq-query.md).  
  
## <a name="see-also"></a>См. также

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
