---
title: Практическое руководство. Написание пользовательской агрегатной функции PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
ms.openlocfilehash: 644d6b6f929e040a0fe688c18c774de6f434c4b3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290776"
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Практическое руководство. Написание пользовательской агрегатной функции PLINQ
Этот пример демонстрирует, как использовать метод <xref:System.Linq.ParallelEnumerable.Aggregate%2A> для применения пользовательской функции агрегирования к исходной последовательности.  
  
> [!WARNING]
> Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. Дополнительные сведения см. в статье [Общее представление об ускорении выполнения в PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 Следующий пример вычисляет стандартное отклонение для последовательности целых чисел.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 В этом примере используется перегрузка стандартного оператора запроса Aggregate, уникального для PLINQ. Эта перегрузка принимает дополнительный <xref:System.Func%603?displayProperty=nameWithType> в качестве третьего входного параметра. Этот делегат объединяет результаты из всех потоков и выполняет окончательный расчет на основе объединенных результатов. В этом примере он складывает суммы из всех потоков.  
  
 Если тело лямбда-выражения состоит из одного выражения, то возвращаемое значение делегата <xref:System.Func%602?displayProperty=nameWithType> принимает значение этого выражения.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
