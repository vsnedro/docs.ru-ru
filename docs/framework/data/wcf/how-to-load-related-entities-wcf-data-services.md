---
title: Практическое руководство. Загрузка связанных сущностей (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: 1ef7fa93b5afdf664f22bd69d3fe3a3b17e98f18
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180716"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Практическое руководство. Загрузка связанных сущностей (службы данных WCF)

Если необходимо загрузить связанные сущности в WCF Data Services, можно использовать <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> метод для <xref:System.Data.Services.Client.DataServiceContext> класса. Можно также использовать метод в <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> , <xref:System.Data.Services.Client.DataServiceQuery%601> чтобы требовать, чтобы связанные сущности были заранее загружены в тот же ответ на запрос.  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  

 Следующий пример иллюстрирует явную загрузку сущности `Customer`, связанной с каждым возвращенным экземпляром `Orders`.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Пример  

 Следующий пример иллюстрирует использование метода <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> для возврата сущности `Order Details`, принадлежащей сущности `Orders`, возвращаемой запросом.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>См. также раздел

- [Выполнение запросов к службе данных](querying-the-data-service-wcf-data-services.md)
