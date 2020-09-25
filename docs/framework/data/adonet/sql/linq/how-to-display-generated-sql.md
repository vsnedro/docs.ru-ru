---
title: Практическое руководство. Как отобразить сформированный код SQL
description: Узнайте, как просмотреть код SQL, созданный для запросов, с помощью свойства Log, чтобы понять LINQ to SQL функциональности и для отладки.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 81f6b9603cc7f8b7863f787272ce6a1af920fa75
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169496"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="2a0eb-103">Практическое руководство. Как отобразить сформированный код SQL</span><span class="sxs-lookup"><span data-stu-id="2a0eb-103">How to: Display Generated SQL</span></span>

<span data-ttu-id="2a0eb-104">Для просмотра кода SQL, созданного для запросов, и изменения обработки используется свойство <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a0eb-104">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="2a0eb-105">Такой подход может оказаться полезным для получения основных сведений о функциях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и для отладки конкретных проблем.</span><span class="sxs-lookup"><span data-stu-id="2a0eb-105">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a0eb-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2a0eb-106">Example</span></span>  

 <span data-ttu-id="2a0eb-107">В следующем примере для отображения кода SQL в окне консоли перед его выполнением использовано свойство <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a0eb-107">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="2a0eb-108">Это свойство можно применять с командами выполнения запросов, вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="2a0eb-108">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="2a0eb-109">Строки из окна консоли отображаются при выполнении приведенного ниже кода Visual Basic или C#.</span><span class="sxs-lookup"><span data-stu-id="2a0eb-109">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```console  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```console  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2a0eb-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a0eb-110">See also</span></span>

- [<span data-ttu-id="2a0eb-111">Поддержка отладки</span><span class="sxs-lookup"><span data-stu-id="2a0eb-111">Debugging Support</span></span>](debugging-support.md)
