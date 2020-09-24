---
title: <synchronousReceive> - элемент
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 2073d115dd87d513a6e48b8b585fed4b49d5bb32
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157178"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="1dd44-102">Элемент \<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="1dd44-102">\<synchronousReceive> element</span></span>

<span data-ttu-id="1dd44-103">Этот элемент конфигурации используется, чтобы задавать поведение времени выполнения при получении сообщений в службе или в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="1dd44-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="1dd44-104">Он не имеет атрибутов или дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="1dd44-104">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="1dd44-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1dd44-105">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dd44-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1dd44-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1dd44-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1dd44-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dd44-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1dd44-108">Attributes</span></span>  

 <span data-ttu-id="1dd44-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1dd44-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1dd44-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1dd44-110">Child Elements</span></span>  

 <span data-ttu-id="1dd44-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1dd44-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dd44-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1dd44-112">Parent Elements</span></span>  
  
|<span data-ttu-id="1dd44-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="1dd44-113">Element</span></span>|<span data-ttu-id="1dd44-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1dd44-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1dd44-115">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1dd44-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dd44-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="1dd44-116">Remarks</span></span>  

 <span data-ttu-id="1dd44-117">Используйте это поведение, чтобы дать указание прослушивателю каналов использовать синхронное получение вместо асинхронного получения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1dd44-117">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="1dd44-118">Windows Communication Foundation (WCF) выдает новый поток для приема для каждого принятого канала.</span><span class="sxs-lookup"><span data-stu-id="1dd44-118">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="1dd44-119">При наличии множества каналов существует вероятность недостатка потоков.</span><span class="sxs-lookup"><span data-stu-id="1dd44-119">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd44-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1dd44-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
