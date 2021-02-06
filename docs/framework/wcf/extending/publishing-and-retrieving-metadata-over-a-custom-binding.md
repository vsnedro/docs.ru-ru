---
description: Дополнительные сведения о публикации и извлечении метаданных с помощью пользовательской привязки
title: Публикация и получение метаданных через пользовательскую привязку
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 26532c3478d8250e9f6ec7dbb9431be5052239b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644129"
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Публикация и получение метаданных через пользовательскую привязку

Класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> поддерживает добавление конечной точки метаданных в службу. Эти конечные точки метаданных могут отвечать на запросы HTTP GET по URL-адресу, который имеет `?wsdl` строку запроса и WS-Transfer запросы GET, как определено в спецификации WS-MetadataExchange (MEX). Конечные точки MEX реализуют контракт <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType>.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Публикация метаданных через настраиваемую привязку.  

 Чтобы включить конечные точки метаданных HTTP GET и HTTPS GET, необходимо присвоить логическое значение <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> или `true`. Привязки для этих конечных точек не могут быть настроены.  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>Однако контракт можно использовать с любой конечной точкой, включая те, которые используют пользовательские привязки, так как <xref:System.ServiceModel.Description.IMetadataExchange> конечные точки идентичны любой другой конечной точке службы Windows Communication Foundation (WCF). Настройка привязки для использования с конечной точкой <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> требует навыков изменения конфигурации привязки, предоставляемой системой, или настройки <xref:System.ServiceModel.Description.IMetadataExchange>.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Получение метаданных через настраиваемую привязку.  

 Метаданные могут быть получены из конечных точек метаданных HTTP Get и HTTPS Get с использованием стандартных запросов HTTP или HTTPS GET.  
  
 Чтобы получить метаданные из конечной точки метаданных MEX, обычно можно использовать одну из стандартных привязок MEX, поддерживаемых WCF. Для получения дополнительной информации см. <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. Тип <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> и средство Svcutil.exe автоматически выбирают одну из стандартных привязок MEX на основе адреса заданной конечной точки метаданных.  
  
 Если конечная точка метаданных MEX использует привязку, отличающуюся от стандартных привязок MEX, существует возможность настроить привязку, используемую классом <xref:System.ServiceModel.Description.MetadataExchangeClient>, используя код или предоставляя конфигурацию конечной точки клиента <xref:System.ServiceModel.Description.IMetadataExchange>. Инструмент Svcutil.exe автоматически загружает из своего файла конфигурации конфигурацию конечной точки клиента <xref:System.ServiceModel.Description.IMetadataExchange> с именем, аналогичным имени схемы URI для адреса конечной точки метаданных.  
  
## <a name="security"></a>Безопасность  

 При публикации метаданных через настраиваемую привязку, убедитесь, что привязка обеспечивает поддержку безопасности, требуемую для метаданных. Например, для предотвращения раскрытия информации и контроля прав клиента на получение метаданных существует возможность дополнительной защиты метаданных и приложения путем настройки конечной точки <xref:System.ServiceModel.Description.IMetadataExchange> таким образом, чтобы требовались шифрование и проверка подлинности. Этот сценарий показан в примере [пользовательской защищенной конечной точки метаданных](../samples/custom-secure-metadata-endpoint.md) .  
  
## <a name="see-also"></a>См. также

- [Защита служб](../securing-services.md)
- [Привязки WS-MetadataExchange](ws-metadataexchange-bindings.md)
- [Практическое руководство. Настройка пользовательской привязки для обмена WS-Metadata](how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [Практическое руководство. Получение метаданных через привязку, не использующую MEX](how-to-retrieve-metadata-over-a-non-mex-binding.md)
