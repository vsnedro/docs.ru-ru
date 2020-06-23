---
title: Публикация метаданных
description: Узнайте, как службы WCF публикуют метаданные путем публикации одной или нескольких конечных точек метаданных, делая их доступными с помощью стандартных протоколов.
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 2aa6d877db4e5b09b4c594e6e87b63fb6c04703b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244963"
---
# <a name="publishing-metadata"></a>Публикация метаданных
Службы Windows Communication Foundation (WCF) публикуют метаданные путем публикации одной или нескольких конечных точек метаданных. Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS-MetadataExchange (MEX) и запросы HTTP/GET. Конечные точки метаданных аналогичны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт и могут быть добавлены в узел службы посредством конфигурации или принудительного кода.  
  
## <a name="publishing-metadata-endpoints"></a>Публикация конечных точек метаданных  
 Чтобы опубликовать конечные точки метаданных для службы WCF, необходимо сначала добавить <xref:System.ServiceModel.Description.ServiceMetadataBehavior> поведение службы в службу. Добавление экземпляра <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> позволяет службе отображать конечные точки метаданных. После добавления поведения службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> можно отображать конечные точки метаданных, поддерживающие протокол MEX или отвечающие на запросы HTTP/GET.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> использует <xref:System.ServiceModel.Description.WsdlExporter> для экспорта метаданных для всех конечных точек службы. Дополнительные сведения об экспорте метаданных из службы см. в разделе [Экспорт и импорт метаданных](exporting-and-importing-metadata.md).  
  
 Поведение службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> добавляет в узел службы экземпляр <xref:System.ServiceModel.Description.ServiceMetadataExtension> в качестве расширения. Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> обеспечивает реализацию протоколов публикации метаданных. Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> также можно использовать для получения метаданных службы во время выполнения, обратившись к свойству <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>.  
  
### <a name="mex-metadata-endpoints"></a>Конечные точки метаданных MEX  
 Чтобы добавить конечные точки метаданных, использующие протокол MEX, следует добавить в основное приложение службы конечные точки службы, которые используют контракт службы `IMetadataExchange`. WCF включает <xref:System.ServiceModel.Description.IMetadataExchange> интерфейс с этим именем контракта службы, который можно использовать как часть модели программирования WCF. Конечные точки WS-MetadataExchange или службы обмена метаданными могут использовать одну из четырех привязок по умолчанию, которые статические методы фабрики предоставляют <xref:System.ServiceModel.Description.MetadataExchangeBindings> классу для сопоставления с привязками по умолчанию, используемыми средствами WCF, такими как Svcutil.exe. Настраивать конечные точки метаданных MEX также можно с помощью пользовательской привязки.  
  
### <a name="http-get-metadata-endpoints"></a>Конечные точки метаданных HTTP GET  
 Чтобы добавить конечную точку метаданных в службу, которая отвечает на запросы HTTP/GET, следует задать свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> в поведении <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> значение `true`. Кроме того, можно настроить конечную точку метаданных, которая использует протокол HTTPS, задав свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> в поведении <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> значение `true`.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Демонстрирует настройку службы WCF для публикации метаданных, чтобы клиенты могли получать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET с помощью `?wsdl` строки запроса.  
  
 [Практическое руководство. Публикация метаданных для службы с использованием кода](how-to-publish-metadata-for-a-service-using-code.md)  
 Демонстрирует, как включить публикацию метаданных для службы WCF в коде, чтобы клиенты могли получать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя `?wsdl` строку запроса.  
  
## <a name="reference"></a>Справочник  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>См. также

- [Экспорт и импорт метаданных](exporting-and-importing-metadata.md)
