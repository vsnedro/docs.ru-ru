---
title: Практическое руководство. Реализация динамических разделов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
ms.openlocfilehash: 1120d846743ac3b89d2d110b4d1abdd0083f9eab
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825745"
---
# <a name="how-to-implement-dynamic-partitions"></a>Практическое руководство. Реализация динамических разделов

Приведенный ниже пример демонстрирует, как реализовать пользовательский <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> с реализацией динамического секционирования, который можно использовать из некоторых перегрузок <xref:System.Threading.Tasks.Parallel.ForEach%2A> и из PLINQ.  
  
## <a name="example"></a>Пример

Каждый раз, когда секция вызывает для перечислителя <xref:System.Collections.IEnumerator.MoveNext%2A>, этот перечислитель предоставляет ей один элемент списка. При работе с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A> секция реализована в виде экземпляра <xref:System.Threading.Tasks.Task>. Поскольку запросы возникают параллельно в нескольких потоках, доступ к текущему индексу синхронизируется.  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

Здесь представлен пример блочного секционирования, в котором каждый блок состоит из одного элемента. Передавая несколько элементов на один запрос, вы снизите риск конфликтов блокировки и, возможно, увеличите производительность. Но использование больших блоков в определенный момент потребует дополнительной логики для балансировки нагрузки, чтобы все потоки оставались равномерно загруженными до полного завершения всех действий.  
  
## <a name="see-also"></a>См. также раздел

* [Пользовательские разделители для PLINQ и TPL](custom-partitioners-for-plinq-and-tpl.md)
* [Практическое руководство. Реализация разделителя для статического секционирования](how-to-implement-a-partitioner-for-static-partitioning.md)
