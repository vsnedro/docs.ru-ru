---
description: Дополнительные сведения о публикации конечных точек метаданных
title: Публикация конечных точек метаданных
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 8204a62413e09c0fbc6effaae1fd752aee397147
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726680"
---
# <a name="publishing-metadata-endpoints"></a>Публикация конечных точек метаданных

Службы Windows Communication Foundation (WCF) публикуют метаданные путем публикации одной или нескольких конечных точек метаданных. Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS-MetadataExchange (MEX) и запросы HTTP/GET. Конечные точки подобны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт, и могут быть добавлены в ведущее приложение службы посредством конфигурации или в коде. Для публикации конечных точек метаданных необходимо добавить в службу поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Демонстрирует настройку службы WCF для публикации метаданных, чтобы клиенты могли получать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET с помощью `?wsdl` строки запроса.  
  
 [Практическое руководство. Публикация метаданных для службы с использованием кода](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Демонстрирует включение публикации метаданных для службы WCF в коде, чтобы клиенты могли получать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET с помощью `?wsdl` строки запроса.  
  
## <a name="see-also"></a>См. также

- [Публикация метаданных](./feature-details/publishing-metadata.md)
