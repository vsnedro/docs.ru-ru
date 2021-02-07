---
description: 'Подробнее о: перехватчики (службы данных WCF)'
title: Перехватчики (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: f73ee498d0419df9e083248802ea52ed050a914b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765078"
---
# <a name="interceptors-wcf-data-services"></a>Перехватчики (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Службы данных WCF позволяет приложению перехватывать сообщения запроса, чтобы можно было добавить в операцию пользовательскую логику. Эта логика может применяться для проверки данных во входящих сообщениях. Можно также дальнейшим образом ограничить область запроса, например вставить специализированные правила проверки подлинности на основе отдельных запросов.  
  
 Перехват выполняется методами службы данных со специальными атрибутами. Эти методы вызываются службы данных WCF в соответствующей точке обработки сообщения. Перехватчики определяются индивидуально для наборов сущностей. Методы перехватчика, в отличие от операций службы, не принимают параметры из запроса. Методы перехвата запросов, которые вызываются при обработке запросов HTTP GET, должны возвращать лямбда-выражение, определяющее, должен ли экземпляр набора сущностей перехватчика возвращаться в результатах запроса. Это выражение используется службой данных для дальнейшего уточнения запрошенного действия. В следующем примере рассмотрено определение перехватчика запроса.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Перехватчики изменений, которые вызываются при обработке операций, не связанных с запросами, должны возвращать значение `void` (`Nothing` в коде Visual Basic). Методы перехватчика изменений должны принимать следующие два параметра.  
  
1. Параметр типа, совместимого с типом сущностей в наборе сущностей. При вызове службой данных перехватчика изменений значение этого параметра будет отражать сведения о сущности, отправленные в запросе.  
  
2. Параметр типа <xref:System.Data.Services.UpdateOperations>. При вызове службой данных перехватчика изменений значение этого параметра будет отражать операцию, которую пытается выполнить запрос.  
  
 В следующем примере рассмотрено определение перехватчика изменений.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Для перехватчиков поддерживаются следующие атрибуты.  
  
 **[Куеринтерцептор (** *EntitySetName* **)]**  
 Методы с атрибутом <xref:System.Data.Services.QueryInterceptorAttribute> вызываются при получении запроса HTTP GET к целевому ресурсу набора сущностей. Эти методы всегда должны возвращать лямбда-выражение в форме `Expression<Func<T,bool>>`.  
  
 **[Чанжеинтерцептор (** *EntitySetName* **)]**  
 Методы с атрибутом <xref:System.Data.Services.ChangeInterceptorAttribute> вызываются при получении запроса HTTP, отличного от HTTP GET, к целевому ресурсу набора сущностей. Эти методы должны всегда возвращать значение `void` (`Nothing` в коде Visual Basic).  
  
 Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также

- [Операции служб](service-operations-wcf-data-services.md)
