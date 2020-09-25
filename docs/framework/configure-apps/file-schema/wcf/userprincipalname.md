---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 353d3e2d88e3515e54deadab85c37ce3be26ef29
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203869"
---
# \<userPrincipalName>

<span data-ttu-id="2bb39-101">Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="2bb39-101">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="2bb39-102">Дополнительные сведения о настройке имени участника-пользователя см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2bb39-102">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="2bb39-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bb39-103">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bb39-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2bb39-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2bb39-105">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2bb39-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bb39-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2bb39-106">Attributes</span></span>  
  
|<span data-ttu-id="2bb39-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2bb39-107">Attribute</span></span>|<span data-ttu-id="2bb39-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2bb39-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2bb39-109">value</span><span class="sxs-lookup"><span data-stu-id="2bb39-109">value</span></span>|<span data-ttu-id="2bb39-110">Имя учетной записи пользователя (которая иногда называется именем входа пользователя) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="2bb39-110">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="2bb39-111">Это стандартный способ входа в домен Windows.</span><span class="sxs-lookup"><span data-stu-id="2bb39-111">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="2bb39-112">Формат: someone@example.com (как для адреса электронной почты).</span><span class="sxs-lookup"><span data-stu-id="2bb39-112">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2bb39-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2bb39-113">Child Elements</span></span>  

 <span data-ttu-id="2bb39-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2bb39-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2bb39-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2bb39-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2bb39-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="2bb39-116">Element</span></span>|<span data-ttu-id="2bb39-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2bb39-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="2bb39-118">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="2bb39-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bb39-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="2bb39-119">Remarks</span></span>  

 <span data-ttu-id="2bb39-120">Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, использует имя участника-пользователя при выполнении проверки подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="2bb39-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bb39-121">Пример</span><span class="sxs-lookup"><span data-stu-id="2bb39-121">Example</span></span>  

 <span data-ttu-id="2bb39-122">Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="2bb39-122">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="2bb39-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2bb39-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="2bb39-124">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="2bb39-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
