---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855180"
---
# \<headers>
<span data-ttu-id="22b6e-101">Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP.</span><span class="sxs-lookup"><span data-stu-id="22b6e-101">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="22b6e-102">К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники.</span><span class="sxs-lookup"><span data-stu-id="22b6e-102">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="22b6e-103">Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов.</span><span class="sxs-lookup"><span data-stu-id="22b6e-103">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="22b6e-104">Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML.</span><span class="sxs-lookup"><span data-stu-id="22b6e-104">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="22b6e-105">Каждый элемент должен представлять собой XML-код правильного формата.</span><span class="sxs-lookup"><span data-stu-id="22b6e-105">Each element has to be well-formed XML.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**  
  
## <a name="syntax"></a><span data-ttu-id="22b6e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22b6e-106">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22b6e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22b6e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="22b6e-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="22b6e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22b6e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22b6e-109">Attributes</span></span>  
 <span data-ttu-id="22b6e-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="22b6e-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22b6e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22b6e-111">Child Elements</span></span>  
 <span data-ttu-id="22b6e-112">Определяемые пользователем XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="22b6e-112">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22b6e-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22b6e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="22b6e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="22b6e-114">Element</span></span>|<span data-ttu-id="22b6e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="22b6e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="22b6e-116">Настраивает разные типы конечных точек.</span><span class="sxs-lookup"><span data-stu-id="22b6e-116">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22b6e-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="22b6e-117">Remarks</span></span>  
 <span data-ttu-id="22b6e-118">Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="22b6e-118">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="22b6e-119">Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.</span><span class="sxs-lookup"><span data-stu-id="22b6e-119">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b6e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="22b6e-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="22b6e-121">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="22b6e-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
