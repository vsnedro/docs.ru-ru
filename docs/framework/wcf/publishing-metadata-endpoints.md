---
title: Публикация конечных точек метаданных
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 5be27a72c87d95e36a5b283e7930ba0a5191a5a1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249765"
---
# <a name="publishing-metadata-endpoints"></a>Публикация конечных точек метаданных

Службы Windows Communication Foundation (WCF) публикуют метаданные путем публикации одной или нескольких конечных точек метаданных. Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS-MetadataExchange (MEX) и запросы HTTP/GET. Конечные точки подобны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт, и могут быть добавлены в ведущее приложение службы посредством конфигурации или в коде. Для публикации конечных точек метаданных необходимо добавить в службу поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Демонстрирует настройку службы WCF для публикации метаданных, чтобы клиенты могли получать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET с помощью `?wsdl` строки запроса.  
  
 [Практическое руководство. Публикация метаданных для службы с использованием кода](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Демонстрирует включение публикации метаданных для службы WCF в коде, чтобы клиенты могли получать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET с помощью `?wsdl` строки запроса.  
  
## <a name="see-also"></a>См. также

- [Публикация метаданных](./feature-details/publishing-metadata.md)
