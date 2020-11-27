---
title: Интеграция с AJAX и поддержка JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: c895a6dedc22a42adb7104927d39090ab6587f37
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266029"
---
# <a name="ajax-integration-and-json-support"></a>Интеграция с AJAX и поддержка JSON

Поддержка Windows Communication Foundation (WCF) для асинхронных сценариев JavaScript и XML (AJAX) и формата данных нотация объектов JavaScript (JSON) позволяет службам WCF предоставлять операции клиентам AJAX. Клиенты AJAX — это веб-страницы, выполняющие код JavaScript и обращающиеся к этим службам WCF с помощью HTTP-запросов. В этом разделе приведены сведения о такой поддержке и способах ее реализации.  
  
 Дополнительные сведения о ASP.NET AJAX и его интеграции с ASP.NET 2,0 см. в разделе [Общие сведения о ASP.NET AJAX](/previous-versions/aspnet/bb398874(v=vs.100)).  
  
## <a name="in-this-section"></a>в этом разделе  

 [Создание служб WCF для ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md)  
 Описывает, как служба WCF может быть предоставлена клиентам AJAX путем добавления соответствующей конечной точки AJAX либо с помощью настройки, либо с помощью фабрики узла службы, настроенной для создания узла службы, который автоматически настраивает конечную точку AJAX.  
  
 [Создание служб WCF AJAX без использования ASP.NET](creating-wcf-ajax-services-without-aspnet.md)  
 Описывает, как создать службу WCF без использования ASP.NET.  
  
 [Поддержка JSON и других форматов передачи данных](support-for-json-and-other-data-transfer-formats.md)  
 Описывается поддержка формата JSON, который обычно используется для обмена сообщениями со службами ASP.NET AJAX (вместо XML).  
  
 [Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 Описывает, как перенести веб-службу ASP.NET с поддержкой AJAX в веб-службу WCF.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [Модель веб-программирования HTTP WCF](wcf-web-http-programming-model.md)
