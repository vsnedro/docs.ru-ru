---
title: Перехватчики (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: 64c5c82f33daf677e58d49655897c392f1f7b7f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204402"
---
# <a name="interceptors-wcf-data-services"></a>Перехватчики (службы данных WCF)

WCF Data Services позволяет приложению перехватывать сообщения запроса, чтобы можно было добавить в операцию пользовательскую логику. Эта логика может применяться для проверки данных во входящих сообщениях. Можно также дальнейшим образом ограничить область запроса, например вставить специализированные правила проверки подлинности на основе отдельных запросов.  
  
 Перехват выполняется методами службы данных со специальными атрибутами. Эти методы вызываются WCF Data Services в соответствующей точке обработки сообщения. Перехватчики определяются индивидуально для наборов сущностей. Методы перехватчика, в отличие от операций службы, не принимают параметры из запроса. Методы перехвата запросов, которые вызываются при обработке запросов HTTP GET, должны возвращать лямбда-выражение, определяющее, должен ли экземпляр набора сущностей перехватчика возвращаться в результатах запроса. Это выражение используется службой данных для дальнейшего уточнения запрошенного действия. В следующем примере рассмотрено определение перехватчика запроса.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Операции служб](service-operations-wcf-data-services.md)
