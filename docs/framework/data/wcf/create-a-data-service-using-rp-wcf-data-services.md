---
title: Практическое руководство. Создание службы данных с использованием поставщика отражений (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 6bab9d9be484cf90cb85df63a1b237b5cc39a5e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152771"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>Практическое руководство. Создание службы данных с использованием поставщика отражений (службы данных WCF)

WCF Data Services позволяет определить модель данных, основанную на произвольных классах, если эти классы предоставляются как объекты, реализующие <xref:System.Linq.IQueryable%601> интерфейс. Дополнительные сведения см. в разделе [поставщики служб данных](data-services-providers-wcf-data-services.md).  
  
## <a name="example"></a>Пример  

 Следующий пример определяет модель данных, включающую сущности `Orders` и `Items`. Класс контейнера сущностей `OrderItemData` имеет два публичных метода, которые возвращают интерфейсы <xref:System.Linq.IQueryable%601>. Эти интерфейсы являются наборами сущностей типа `Orders` и типами сущностей `Items`. Сущность `Order` может включать несколько сущностей `Items`, поэтому тип сущности `Orders` имеет свойство навигации `Items`, возвращающее коллекцию объектов `Items`. Класс контейнера сущностей `OrderItemData` является универсальным типом класса <xref:System.Data.Services.DataService%601>, производным которого является класс `OrderItems` службы данных.  
  
> [!NOTE]
> Поскольку пример демонстрирует поставщика данных в памяти и изменения не сохраняются за пределами текущих экземпляров объектов, реализация интерфейса <xref:System.Data.Services.IUpdatable> не приносит никаких выгод. Пример, в котором реализуется <xref:System.Data.Services.IUpdatable> интерфейс, см. [в разделе инструкции. Создание службы данных с помощью LINQ to SQL источника данных](create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Создание службы данных с использованием источника данных LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md)
- [Поставщики служб данных](data-services-providers-wcf-data-services.md)
- [Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET](create-a-data-service-using-an-adonet-ef-data-wcf.md)
