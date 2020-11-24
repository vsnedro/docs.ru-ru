---
title: Практическое руководство. Задание режима выполнения в PLINQ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: d45aaa04e08c0ada77a01d4f67379c9b1b8773e2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825550"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Практическое руководство. Задание режима выполнения в PLINQ

В этом примере показано, как принудительно отключить эвристический анализ PLINQ по умолчанию, чтобы параллелизовать запрос независимо от его формы.  
  
> [!NOTE]
> Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. См. дополнительные сведения об [ускорении выполнения в PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ разработан для того, чтобы применить преимущества параллелизации. Но не все запросы станут быстрее при параллельном выполнении. Например, если запрос содержит только один пользовательский делегат с небольшим числом задач, последовательно запрос выполняется быстрее. Это связано с тем, что нагрузка на управление параллельным выполнением превышает полученную выгоду от ускорения работы. По этой причине PLINQ не применяет параллелизацию к каждому запросу автоматически. Сначала он проверяет форму запроса и входящие в него операторы. Исходя из этих результатов анализа, PLINQ в стандартном режиме выполнения самостоятельно решает, нужно ли выполнять параллельно весь запрос или некоторые его элементы. Но в некоторых случаях у вас есть больше сведений о запросе, чем доступно PLINQ на основе такого анализа. Например, вы знаете, что делегат затратный и в любом случае выиграет от применения параллелизации. В таких случаях вы можете применить метод <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> со значением <xref:System.Linq.ParallelExecutionMode.ForceParallelism>, чтобы PLINQ всегда выполнял этот запрос параллельно.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте и вставьте этот код в [пример данных PLINQ](plinq-data-sample.md), затем вызовите этот метод из `Main`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
