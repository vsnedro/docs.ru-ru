---
description: Дополнительные сведения о выражениях в запросах LINQ to Entities
title: Выражения в запросах LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 3ab9e04adb7e823538638ae262f0e481b6948a24
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786372"
---
# <a name="expressions-in-linq-to-entities-queries"></a>Выражения в запросах LINQ to Entities

Выражение представляет собой фрагмент кода, результатом вычисления которого является единственное значение, объект, метод или пространство имен. Выражение может содержать литеральное значение, вызов метода, оператор с операндами или простое имя. Простые имена могут быть именами переменной, элемента типа, параметра метода, пространства имен или типа. В выражениях могут использоваться операторы, которые, в свою очередь, используют в качестве параметров другие выражения или вызовы методов, параметрами которых являются другие вызовы методов. Таким образом, выражения могут быть как простыми, так и очень сложными.  
  
 В запросах LINQ to Entities выражения могут содержать все, что разрешено типами в <xref:System.Linq.Expressions> пространстве имен, включая лямбда-выражения. Выражения, которые могут использоваться в запросах LINQ to Entities, представляют собой надмножество выражений, которые можно использовать для запроса Entity Framework. выражения, которые являются частью запросов к Entity Framework, ограничены операциями, поддерживаемыми `ObjectQuery<T>` и базовым источником данных.  
  
 В следующем примере сравнение в предложении `Where` является следующим выражением.  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> Отдельные языковые конструкции, такие как C# `unchecked` , не имеют смысла в LINQ to Entities.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Константные выражения](constant-expressions.md)  
  
 [Выражения сравнения](comparison-expressions.md)  
  
 [Сравнения NULL](null-comparisons.md)  
  
 [Выражения инициализации](initialization-expressions.md)  
  
 [Связи, свойства навигации и внешние ключи](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../index.md)
