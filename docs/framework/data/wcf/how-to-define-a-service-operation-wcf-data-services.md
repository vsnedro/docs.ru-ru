---
description: Дополнительные сведения см. в статье как определить операцию службы (службы данных WCF).
title: Практическое руководство. Определение операции службы (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: 9fcad3a31ea5b439c248ba103cbf4ddd75b8109a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765624"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a>Практическое руководство. Определение операции службы (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Службы данных WCF предоставить методы, определенные на сервере как операции службы. Операции службы позволяют службе данных предоставить доступ через URI к методу, определенному на сервере. Чтобы определить операцию службы, примените `WebGet]` `[WebInvoke]` к методу атрибут [или. Для поддержки операторов запросов операция службы должна возвращать <xref:System.Linq.IQueryable%601> экземпляр. Операции службы могут обращаться к базовому источнику данных через свойство <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> объекта <xref:System.Data.Services.DataService%601>. Дополнительные сведения см. в разделе [операции службы](service-operations-wcf-data-services.md).

Пример в этом разделе определяет операцию службы с именем `GetOrdersByCity`, возвращающую фильтрованный экземпляр <xref:System.Linq.IQueryable%601>`Orders` и связанные объекты `Order_Details`. Пример обращается к экземпляру <xref:System.Data.Objects.ObjectContext>, являющемуся источником данных для образца службы данных Northwind. Эта служба создается при завершении [краткого руководства по службы данных WCF](quickstart-wcf-data-services.md).

### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a>Определение операции службы в службе данных Northwind

1. Откройте в проекте службы данных Northwind файл Northwind.svc.

2. Определите в классе `Northwind` метод операции службы с именем `GetOrdersByCity`, как показано дальше:

     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

3. Добавьте в метод `InitializeService` класса `Northwind` следующий код, разрешающий доступ к операции службы:

     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

### <a name="to-query-the-getordersbycity-service-operation"></a>Запрос к операции службы GetOrdersByCity

- Введите в веб-браузере один из следующих URI для вызова операции службы, определенной в следующем примере:

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`

## <a name="example"></a>Пример

В следующем примере реализована операция службы с именем `GetOrderByCity` в службе данных Northwind. Эта операция использует ADO.NET Entity Framework для возвращения набора сущностей `Orders` и связанных объектов `Order_Details` в виде экземпляра <xref:System.Linq.IQueryable%601> на основе переданного названия города.

> [!NOTE]
> Операторы запросов поддерживаются для этой конечной точки операции службы, потому что метод возвращает экземпляр <xref:System.Linq.IQueryable%601>.

[!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperation)]
[!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperation)]

## <a name="see-also"></a>См. также

- [Определение служб данных WCF](defining-wcf-data-services.md)
