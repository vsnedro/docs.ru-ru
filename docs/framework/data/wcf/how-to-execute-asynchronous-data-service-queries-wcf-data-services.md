---
description: Дополнительные сведения см. в статье как выполнять запросы асинхронных служб данных (службы данных WCF)
title: Практическое руководство. Выполнение асинхронных запросов к службе данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: 35300de319673b29484dc981b5d6d51c964ad908
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765351"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Практическое руководство. Выполнение асинхронных запросов к службе данных (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

С помощью клиентской библиотеки службы данных WCF можно асинхронно выполнять операции типа "клиент-сервер", такие как выполнение запросов и сохранение изменений. Дополнительные сведения см. в разделе [асинхронные операции](asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
> В приложении, в котором метод обратного вызова должен быть вызван из определенного потока, необходимо выполнить явный маршалинг выполнения метода <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>. Дополнительные сведения см. в разделе [асинхронные операции](asynchronous-operations-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по службы данных WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  

 Следующий пример иллюстрирует выполнение асинхронного запроса путем вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> для запуска запроса. Встроенный делегат вызывает метод <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> для отображения результатов запроса.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
