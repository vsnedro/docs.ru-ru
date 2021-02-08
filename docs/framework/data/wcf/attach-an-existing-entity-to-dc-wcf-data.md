---
description: Дополнительные сведения см. в статье как присоединить существующую сущность к DataServiceContext (службы данных WCF)
title: Практическое руководство. Присоединение существующей сущности к контексту DataServiceContext (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 039225ec992a4ddd23fd9f7013e04562f6fe72a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766599"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Практическое руководство. Присоединение существующей сущности к контексту DataServiceContext (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Если сущность уже существует в службе данных, клиентская библиотека службы данных WCF позволяет присоединить объект, который представляет сущность непосредственно к, <xref:System.Data.Services.Client.DataServiceContext> без предварительного выполнения запроса. Дополнительные сведения см. [в разделе Обновление службы данных](updating-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по службы данных WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  

 Следующий пример иллюстрирует создание существующего объекта `Customer`, содержащего изменения, которые должны быть сохранены в службе данных. Объект присоединяется к контексту, и вызывается метод <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>, помечающий присоединенный объект как <xref:System.Data.Services.Client.EntityStates.Modified> перед вызовом метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
