---
description: Дополнительные сведения см. в статье как использовать хранимые процедуры, сопоставленные с несколькими результирующими формами.
title: Практическое руководство. Как использовать хранимые процедуры, сопоставленные с несколькими результирующими формами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 9faf80e565656120a2601b30424df80ca10913e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785826"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a>Практическое руководство. Как использовать хранимые процедуры, сопоставленные с несколькими результирующими формами

Если хранимая процедура возвращает несколько результирующих форм, тип возвращаемых данных не может быть строго типизированным в соответствии с отдельной формой проекции. Хотя [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] может формировать все возможные типы проекций, он не может понять порядок, в котором они будут возвращены.  
  
 Этот сценарий противоположен сценарию использования хранимых процедур, которые последовательно возвращают несколько результирующих форм. Дополнительные сведения см. [в разделе инструкции. Использование хранимых процедур, сопоставленных с последовательной фигурой результатов](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).  
  
 Чтобы указать набор типов, которые могут возвращать хранимые процедуры, возвращающие несколько типов результатов, к этим процедурам применяется атрибут <xref:System.Data.Linq.Mapping.ResultTypeAttribute>.  
  
## <a name="example"></a>Пример  

 В следующем примере SQL-кода результирующая форма зависит от входных данных (`shape =1` или `shape = 2`). Какая проекция будет возвращена первой, неизвестно.  
  
``` sql
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a>Пример  

 Для выполнения этой хранимой процедуры следует использовать код, который выглядит следующим образом:  
  
> [!NOTE]
> Необходимо использовать шаблон <xref:System.Data.Linq.IMultipleResults.GetResult%2A> для получения перечислителя правильного типа на основе сведений о хранимой процедуре.  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Хранимые процедуры](stored-procedures.md)
