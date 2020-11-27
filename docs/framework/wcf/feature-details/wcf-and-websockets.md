---
title: WCF и WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: 2ee27eef015ee8c2fbee8360b444343a1c757097
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281590"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="6dfeb-102">WCF и WebSockets</span><span class="sxs-lookup"><span data-stu-id="6dfeb-102">WCF and WebSockets</span></span>

<span data-ttu-id="6dfeb-103">В .NET Framework версии 4.5 добавлена поддержка WebSockets в службах Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="6dfeb-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="6dfeb-104">WebSockets - это эффективная, основанная на стандартах технология, обеспечивающая двусторонний обмен сообщениями через стандартные HTTP-порты 80 и 443.</span><span class="sxs-lookup"><span data-stu-id="6dfeb-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="6dfeb-105">Использование стандартных HTTP-портов позволяет WebSockets устанавливать связь по сети через посредников.</span><span class="sxs-lookup"><span data-stu-id="6dfeb-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="6dfeb-106">Были добавлены две стандартные привязки для поддержки обмена данными через транспорт WebSocket.</span><span class="sxs-lookup"><span data-stu-id="6dfeb-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="6dfeb-107"><xref:System.ServiceModel.NetHttpBinding> и <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="6dfeb-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="6dfeb-108">Параметры, относящиеся к WebSocket, можно настроить в <xref:System.ServiceModel.Channels.HttpTransportBindingElement> с помощью <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="6dfeb-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6dfeb-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="6dfeb-109">In This Section</span></span>  

 [<span data-ttu-id="6dfeb-110">Использование NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="6dfeb-110">Using the NetHttpBinding</span></span>](using-the-nethttpbinding.md)  
 <span data-ttu-id="6dfeb-111">Описывает <xref:System.ServiceModel.NetHttpBinding> и его настройку.</span><span class="sxs-lookup"><span data-stu-id="6dfeb-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="6dfeb-112">Практическое руководство. Создание службы WCF, обменивающейся данными через WebSockets</span><span class="sxs-lookup"><span data-stu-id="6dfeb-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="6dfeb-113">Описывает процесс создания службы WCF, обменивающейся данными через Websockets.</span><span class="sxs-lookup"><span data-stu-id="6dfeb-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6dfeb-114">Справочник</span><span class="sxs-lookup"><span data-stu-id="6dfeb-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6dfeb-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6dfeb-115">Related Sections</span></span>
