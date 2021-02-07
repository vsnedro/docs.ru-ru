---
description: Дополнительные сведения см. в статье как загружать результаты в выгружаемом страничном порядке (службы данных WCF)
title: Практическое руководство. Загрузка результатов, разбитых на страницы (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
ms.openlocfilehash: 2a5ba738a63de11045dec78f4381b93c844a4fc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765273"
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>Практическое руководство. Загрузка результатов, разбитых на страницы (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Службы данных WCF позволяет службе данных ограничивать количество сущностей, возвращаемых в одном канале ответа. Если это происходит, последняя запись в канале содержит ссылку на следующую страницу данных. Получить URI для следующей страницы можно, вызвав метод <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> объекта <xref:System.Data.Services.Client.QueryOperationResponse%601>, возвращенного при выполнении запроса <xref:System.Data.Services.Client.DataServiceQuery%601>. URI, представленный этим объектом, можно затем использовать для загрузки следующей страницы результатов. Дополнительные сведения см. в разделе [Загрузка отложенного содержимого](loading-deferred-content-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по службы данных WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  

 Этот пример использует цикл `do…while` для загрузки сущностей `Customers` из разбитых на страницы результатов службы данных.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>Пример  

 Этот пример возвращает связанные сущности `Orders` вместе с каждой сущностью `Customers` и использует цикл `do…while` для загрузки страниц сущностей `Customers`, а также вложенный цикл `while` для загрузки страниц связанных сущностей `Orders` из службы данных.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>См. также

- [Загрузка отложенного содержимого](loading-deferred-content-wcf-data-services.md)
- [Практическое руководство. Загрузка связанных сущностей](how-to-load-related-entities-wcf-data-services.md)
