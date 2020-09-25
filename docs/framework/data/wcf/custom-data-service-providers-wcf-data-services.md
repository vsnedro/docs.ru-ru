---
title: Специализированные поставщики служб данных (службы WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: 4c92bf2f4e75b78cd6236c023246cc6c999086fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186696"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Специализированные поставщики служб данных (службы WCF Data Services)

WCF Data Services включает набор поставщиков, позволяющих определить модель данных на основе типов данных с поздним связыванием.  
  
|Поставщик|Описание|  
|--------------|-----------------|  
|Поставщик метаданных|Это базовый специализированный поставщик служб данных, позволяющий определить специализированную модель данных во время выполнения путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|Поставщик запросов|Этот поставщик позволяет выполнять запросы к специализированной модели данных, определенной при помощи интерфейса <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>. Поставщик запросов создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.|  
|Поставщик обновлений|Этот поставщик позволяет производить обновления типов, предоставляемых специализированным поставщиком служб данных, а также управлять параллелизмом. Поставщик обновлений создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>.|  
|Поставщик подкачки|Этот поставщик используется вместе со специализированным поставщиком служб данных для поддержки подкачки страниц на сервере. Поставщик подкачки для специализированной службы данных создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServicePagingProvider>.|  
|Потоковый поставщик|Этот поставщик позволяет предоставлять данные больших двоичных объектов в виде потока. Потоковый поставщик создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Поставщик потока также может использоваться вместе с платформой Entity Framework и поставщиками отражений источников данных. Дополнительные сведения см. в разделе [Streaming Provider](streaming-provider-wcf-data-services.md).|  
  
## <a name="see-also"></a>См. также раздел

- [Поставщики служб данных](data-services-providers-wcf-data-services.md)
- [Поставщик Entity Framework](entity-framework-provider-wcf-data-services.md)
- [Поставщик отражения](reflection-provider-wcf-data-services.md)
