---
title: Практическое руководство. Использование Parallel.Invoke для выполнения параллельных операций
description: Узнайте, как использовать метод Parallel.Invoke из библиотеки параллельных задач (TPL), который выполняет параллельные операции с общим источником данных в .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 6ec8f03216cc6225e909f5dc3128469047826166
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825485"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Практическое руководство. Использование Parallel.Invoke для выполнения параллельных операций

В этом примере показывается, как параллелизовать операции с помощью метода <xref:System.Threading.Tasks.Parallel.Invoke%2A> в библиотеке параллельных задач. В общем источнике данных выполняются три операции. Они могут выполняться параллельно простым способом, поскольку ни одна из этих операций не изменяет источник.

> [!NOTE]
> В этой документации для определения делегатов в библиотеке параллельных задач используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. статью [Лямбда-выражения в PLINQ и библиотеке параллельных задач](lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Пример

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

С помощью метода <xref:System.Threading.Tasks.Parallel.Invoke%2A> можно просто указать, какие действия должны выполняться параллельно, и среда выполнения обработает все сведения по планированию потока, включая автоматическое масштабирование на число ядер в главном компьютере.

В этом примере параллелизуются операции, но не данные. Как вариант можно параллелизовать запросы LINQ с помощью PLINQ и выполнять эти запросы последовательно. Кроме того, можно параллелизовать данные с помощью PLINQ. Другим вариантом является параллелизация запросов и задач. Хотя итоговая нагрузка может снизить производительность главных компьютеров с относительно небольшим числом процессоров, масштабирование выполняется лучше на компьютерах с большим числом процессоров.

## <a name="compile-the-code"></a>Компиляция кода

Скопируйте и вставьте весь пример в проект Microsoft Visual Studio и нажмите клавишу **F5**.

## <a name="see-also"></a>См. также

- [Параллельное программирование](index.md)
- [Практическое руководство. Отмена задачи и ее дочерних элементов](how-to-cancel-a-task-and-its-children.md)
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
