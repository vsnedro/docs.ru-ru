---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854990"
---
# \<servicePrincipalName>
<span data-ttu-id="3357b-101">Указывает идентификацию службы по имени субъекта-службы (SPN).</span><span class="sxs-lookup"><span data-stu-id="3357b-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="3357b-102">Дополнительные сведения о настройке имени субъекта-службы см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="3357b-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="3357b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3357b-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3357b-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3357b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="3357b-105">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3357b-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3357b-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3357b-106">Attributes</span></span>  
  
|<span data-ttu-id="3357b-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3357b-107">Attribute</span></span>|<span data-ttu-id="3357b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="3357b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3357b-109">value</span><span class="sxs-lookup"><span data-stu-id="3357b-109">value</span></span>|<span data-ttu-id="3357b-110">Имя, по которому клиент однозначно определяет экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="3357b-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="3357b-111">Если на компьютерах в лесу установлено несколько экземпляров службы, то каждый экземпляр должен иметь свое имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="3357b-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="3357b-112">Каждый экземпляр службы может иметь несколько имен участников-служб при наличии нескольких имен, которые могут использоваться клиентами для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3357b-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3357b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3357b-113">Child Elements</span></span>  
 <span data-ttu-id="3357b-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3357b-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3357b-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3357b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3357b-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="3357b-116">Element</span></span>|<span data-ttu-id="3357b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="3357b-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="3357b-118">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="3357b-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3357b-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="3357b-119">Remarks</span></span>  
 <span data-ttu-id="3357b-120">Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, использует имя субъекта-службы при выполнении проверки подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="3357b-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3357b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3357b-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="3357b-122">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="3357b-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
