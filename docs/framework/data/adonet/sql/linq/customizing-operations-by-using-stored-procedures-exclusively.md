---
title: Настройка операций за счет исключительного использования хранимых процедур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 78db5cf448a19056d7265ab84d97d055748c3faa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164328"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="e66a5-102">Настройка операций за счет исключительного использования хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="e66a5-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>

<span data-ttu-id="e66a5-103">Распространенным сценарием является доступ к данным с использованием только хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="e66a5-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e66a5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e66a5-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e66a5-105">Описание</span><span class="sxs-lookup"><span data-stu-id="e66a5-105">Description</span></span>  

 <span data-ttu-id="e66a5-106">Вы можете изменить пример, предоставленный в разделе [Настройка операций, используя хранимые процедуры](customizing-operations-by-using-stored-procedures.md) , заменив даже первый запрос (который вызывает динамическое выполнение SQL) вызовом метода, который создает оболочку для хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e66a5-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="e66a5-107">Предположим, что `CustomersByCity` является методом, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e66a5-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e66a5-108">Код</span><span class="sxs-lookup"><span data-stu-id="e66a5-108">Code</span></span>  

 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="e66a5-109">Следующий код выполняется без динамического SQL.</span><span class="sxs-lookup"><span data-stu-id="e66a5-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e66a5-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e66a5-110">See also</span></span>

- [<span data-ttu-id="e66a5-111">Ответственность разработчика при переопределении поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e66a5-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)
