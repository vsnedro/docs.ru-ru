---
title: Интеграция с AJAX и поддержка JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: f1748372af520955c139dffb2e6e80ae066c9397
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536071"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="1fc17-102">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="1fc17-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="1fc17-103">Поддержка Windows Communication Foundation (WCF) для асинхронных сценариев JavaScript и XML (AJAX) и формата данных нотация объектов JavaScript (JSON) позволяет службам WCF предоставлять операции клиентам AJAX.</span><span class="sxs-lookup"><span data-stu-id="1fc17-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="1fc17-104">Клиенты AJAX — это веб-страницы, выполняющие код JavaScript и обращающиеся к этим службам WCF с помощью HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="1fc17-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="1fc17-105">В этом разделе приведены сведения о такой поддержке и способах ее реализации.</span><span class="sxs-lookup"><span data-stu-id="1fc17-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="1fc17-106">Дополнительные сведения о ASP.NET AJAX и его интеграции с ASP.NET 2,0 см. в разделе [Общие сведения о ASP.NET AJAX](/previous-versions/aspnet/bb398874(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1fc17-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](/previous-versions/aspnet/bb398874(v=vs.100)).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1fc17-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="1fc17-107">In This Section</span></span>  
 [<span data-ttu-id="1fc17-108">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="1fc17-108">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="1fc17-109">Описывает, как служба WCF может быть предоставлена клиентам AJAX путем добавления соответствующей конечной точки AJAX либо с помощью настройки, либо с помощью фабрики узла службы, настроенной для создания узла службы, который автоматически настраивает конечную точку AJAX.</span><span class="sxs-lookup"><span data-stu-id="1fc17-109">Describes how a WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="1fc17-110">Создание служб WCF AJAX без использования ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1fc17-110">Creating WCF AJAX Services without ASP.NET</span></span>](creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="1fc17-111">Описывает, как создать службу WCF без использования ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1fc17-111">Describes how to create a WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="1fc17-112">Поддержка JSON и других форматов передачи данных</span><span class="sxs-lookup"><span data-stu-id="1fc17-112">Support for JSON and Other Data Transfer Formats</span></span>](support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="1fc17-113">Описывается поддержка формата JSON, который обычно используется для обмена сообщениями со службами ASP.NET AJAX (вместо XML).</span><span class="sxs-lookup"><span data-stu-id="1fc17-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="1fc17-114">Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="1fc17-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="1fc17-115">Описывает, как перенести веб-службу ASP.NET с поддержкой AJAX в веб-службу WCF.</span><span class="sxs-lookup"><span data-stu-id="1fc17-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc17-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1fc17-116">See also</span></span>

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [<span data-ttu-id="1fc17-117">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="1fc17-117">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
