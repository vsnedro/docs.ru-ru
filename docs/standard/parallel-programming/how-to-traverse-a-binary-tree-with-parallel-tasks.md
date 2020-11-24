---
title: Практическое руководство. Переход по двоичному дереву с помощью параллельных задач
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
ms.openlocfilehash: ca70021c7d071abe480cb4ed866e34f171cc3b45
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825537"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Практическое руководство. Переход по двоичному дереву с помощью параллельных задач
В следующем примере представлено два способа применить параллельные задачи для обхода древовидной структуры данных. Создание такого дерева остается вам в качестве упражнения.  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Два представленных здесь метода функционально эквивалентны. Используя метод <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> для создания и выполнения задач, вы можете получить от этих задач дескриптор и применить его для ожидания задач и обработки исключений.  
  
## <a name="see-also"></a>См. также раздел

- [Библиотека параллельных задач (TPL)](task-parallel-library-tpl.md)
