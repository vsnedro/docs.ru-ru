---
description: Дополнительные сведения см. в статье как определить число сущностей, возвращаемых запросом (службы данных WCF)
title: Практическое руководство. Определение количества сущностей, возвращаемых запросом (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
ms.openlocfilehash: f8eb305bc515d1d69025ce3bcd0a6a9f3baf8232
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794992"
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>Практическое руководство. Определение количества сущностей, возвращаемых запросом (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

С помощью службы данных WCF можно определить количество сущностей, которые находятся в наборе сущностей, заданном с помощью URI запроса. Это число можно включить в результат запроса или представить как целое значение. Дополнительные сведения см. [в разделе запросы к службе данных](querying-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по службы данных WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  

 В этом примере запрос выполняется после вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>. Свойство <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> возвращает число сущностей в наборе сущностей `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>Пример  

 В данном примере метод <xref:System.Linq.Enumerable.Count%2A> вызывается для возвращения только целого значения числа сущностей в наборе сущностей `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>См. также

- [Выполнение запросов к службе данных](querying-the-data-service-wcf-data-services.md)
