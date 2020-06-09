---
title: Модель веб-программирования HTTP WCF
ms.date: 03/30/2017
helpviewer_keywords:
- web services programming model [WCF]
- POX
- REST
ms.assetid: 2312a8d3-b66e-4623-ba42-978434300c7f
ms.openlocfilehash: dd9cc282750e59e5ccbfec428c7252ab9689395f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589855"
---
# <a name="wcf-web-http-programming-model"></a><span data-ttu-id="04256-102">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="04256-102">WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="04256-103">Модель программирования веб-HTTP Windows Communication Foundation (WCF) позволяет разработчикам предоставлять операции службы WCF конечным точкам, не являющимся SOAP.</span><span class="sxs-lookup"><span data-stu-id="04256-103">The Windows Communication Foundation (WCF) Web HTTP Programming Model allows developers to expose WCF service operations to non-SOAP endpoints.</span></span> <span data-ttu-id="04256-104">Эта возможность подробно описана в следующих подразделах.</span><span class="sxs-lookup"><span data-stu-id="04256-104">The topics in this section examine the feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04256-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="04256-105">In This Section</span></span>  
 [<span data-ttu-id="04256-106">Общие сведения о модели программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="04256-106">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)  
 <span data-ttu-id="04256-107">Содержит общие сведения о модели веб-программирования HTTP для Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="04256-107">Provides an overview of the Windows Communication Foundation (WCF) Web HTTP Programming Model.</span></span>  
  
 [<span data-ttu-id="04256-108">Объектная модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="04256-108">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)  
 <span data-ttu-id="04256-109">Описание модели программирования веб-HTTP Windows Communication Foundation (WCF) и ее работы.</span><span class="sxs-lookup"><span data-stu-id="04256-109">Discusses the Windows Communication Foundation (WCF) Web HTTP Programming Model and how it works.</span></span>  
  
 [<span data-ttu-id="04256-110">Практическое руководство. Как создать простую веб-службу WCF HTTP</span><span class="sxs-lookup"><span data-stu-id="04256-110">How to: Create a Basic WCF Web HTTP Service</span></span>](how-to-create-a-basic-wcf-web-http-service.md)  
 <span data-ttu-id="04256-111">Порядок написания простой службы, предоставляющей конечную точку, не являющуюся конечной точкой SOAP.</span><span class="sxs-lookup"><span data-stu-id="04256-111">Describes how to write a basic service that exposes a non-SOAP endpoint.</span></span>  
  
 [<span data-ttu-id="04256-112">Практическое руководство. Предоставление контрактов SOAP- и веб-клиентам</span><span class="sxs-lookup"><span data-stu-id="04256-112">How to: Expose a Contract to SOAP and Web Clients</span></span>](how-to-expose-a-contract-to-soap-and-web-clients.md)  
 <span data-ttu-id="04256-113">Порядок написания простой службы, предоставляющей один и тот же контракт клиентам SOAP и клиентам, не работающим по протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="04256-113">Describes how to write a basic service that exposes the same contract to both SOAP and non-SOAP clients.</span></span>  
  
 [<span data-ttu-id="04256-114">UriTemplate и UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="04256-114">UriTemplate and UriTemplateTable</span></span>](uritemplate-and-uritemplatetable.md)  
 <span data-ttu-id="04256-115">Описание управления универсальными кодами ресурсов (URI) с помощью классов <xref:System.UriTemplate> и <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="04256-115">Describes how to control URIs using <xref:System.UriTemplate> and <xref:System.UriTemplateTable>.</span></span>  
  
 [<span data-ttu-id="04256-116">Поддержка кэширования для веб-служб HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="04256-116">Caching Support for WCF Web HTTP Services</span></span>](caching-support-for-wcf-web-http-services.md)  
 <span data-ttu-id="04256-117">Описывает, как указать порядок кэширования для веб-службы HTTP WCF.</span><span class="sxs-lookup"><span data-stu-id="04256-117">Describes how to specify caching behavior for a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="04256-118">Форматирование веб-объектов HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="04256-118">WCF Web HTTP Formatting</span></span>](wcf-web-http-formatting.md)  
 <span data-ttu-id="04256-119">Описывает, как указать формат ответа от веб-службы HTTP WCF.</span><span class="sxs-lookup"><span data-stu-id="04256-119">Describes how to specify the format of the response from a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="04256-120">Обработка ошибок веб-протокола HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="04256-120">WCF Web HTTP Error Handling</span></span>](wcf-web-http-error-handling.md)  
 <span data-ttu-id="04256-121">Описывает, как возвращать ошибки веб-клиентам WCF, включающие коды состояния HTTP и дополнительные, определяемые пользователями данные ошибок.</span><span class="sxs-lookup"><span data-stu-id="04256-121">Describes how to return errors to WCF Web clients including HTTP status codes and additional user-defined error data.</span></span>  
  
 [<span data-ttu-id="04256-122">Вызов службы в стиле REST из службы WCF</span><span class="sxs-lookup"><span data-stu-id="04256-122">Calling a REST-style service from a WCF service</span></span>](calling-a-rest-style-service-from-a-wcf-service.md)  
 <span data-ttu-id="04256-123">Описывает, как вызвать REST-службу из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="04256-123">Describes how to call a REST-style service from inside a WCF service.</span></span>
