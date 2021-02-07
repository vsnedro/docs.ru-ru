---
description: Дополнительные сведения см. в статье Определение связей между сущностями (службы данных WCF).
title: Практическое руководство. Определение связей сущностей (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: cc255524-1534-4fae-b83c-250933d5a72b
ms.openlocfilehash: 08add639fe333d4892737c64b12ca370129d0bf7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765520"
---
# <a name="how-to-define-entity-relationships-wcf-data-services"></a>Практическое руководство. Определение связей сущностей (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

При добавлении новой сущности в службы данных WCF любые связи между новой сущностью и связанными сущностями не определяются автоматически. Пользователь может создать и изменить связи между экземплярами сущностей и отразить эти изменения в службе данных с помощью клиентской библиотеки. Дополнительные сведения см. [в разделе Обновление службы данных](updating-the-data-service-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по службы данных WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  

 В следующем примере создается новый экземпляр объекта и вызывается метод <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> контекста <xref:System.Data.Services.Client.DataServiceContext> для создания в контексте нового элемента и ссылки на связанный с ним заказ. Сообщение HTTP POST отправляется в службу данных при вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="example"></a>Пример  

 Следующий пример иллюстрирует использование метода <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> для добавления объекта `Order_Details` к связанному объекту `Orders` со ссылкой на конкретный объект `Products`. Методы <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> и <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> определяют связи. В этом примере также явно заданы свойства навигации объекта `Order_Details`.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorder)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorder)]  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
- [Практическое руководство. Добавление, изменение и удаление сущностей](how-to-add-modify-and-delete-entities-wcf-data-services.md)
