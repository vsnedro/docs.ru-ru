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
# <a name="how-to-display-generated-sql"></a>Практическое руководство. Как отобразить сформированный код SQL

Для просмотра кода SQL, созданного для запросов, и изменения обработки используется свойство <xref:System.Data.Linq.DataContext.Log%2A>. Такой подход может оказаться полезным для получения основных сведений о функциях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и для отладки конкретных проблем.  
  
## <a name="example"></a>Пример  

 В следующем примере для отображения кода SQL в окне консоли перед его выполнением использовано свойство <xref:System.Data.Linq.DataContext.Log%2A>.  Это свойство можно применять с командами выполнения запросов, вставки, обновления и удаления.  
  
 Строки из окна консоли отображаются при выполнении приведенного ниже кода Visual Basic или C#.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Поддержка отладки](debugging-support.md)
