---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: e49a564c9793b371425b2b787586bb9d3cbed58b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "77452231"
---
# \<dns>
<span data-ttu-id="8991a-101">Задает ожидаемое удостоверение сервера.</span><span class="sxs-lookup"><span data-stu-id="8991a-101">Specifies the expected identity of the server.</span></span> <span data-ttu-id="8991a-102">Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.</span><span class="sxs-lookup"><span data-stu-id="8991a-102">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="8991a-103">Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.</span><span class="sxs-lookup"><span data-stu-id="8991a-103">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="8991a-104">Дополнительные сведения о задании значения элемента см. в разделе [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="8991a-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**  
  
## <a name="syntax"></a><span data-ttu-id="8991a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8991a-105">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8991a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8991a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8991a-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8991a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8991a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8991a-108">Attributes</span></span>  
  
|<span data-ttu-id="8991a-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8991a-109">Attribute</span></span>|<span data-ttu-id="8991a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8991a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8991a-111">value</span><span class="sxs-lookup"><span data-stu-id="8991a-111">value</span></span>|<span data-ttu-id="8991a-112">Сервер DNS сертификата.</span><span class="sxs-lookup"><span data-stu-id="8991a-112">The DNS of the certificate.</span></span> <span data-ttu-id="8991a-113">Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.</span><span class="sxs-lookup"><span data-stu-id="8991a-113">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="8991a-114">Пользователи могут запоминать отображаемые имена, например `https://go.microsoft.com/fwlink/?prd=10929` или `https://go.microsoft.com/fwlink/?LinkID=96165` , проще, чем адреса на основе чисел, например 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="8991a-114">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8991a-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8991a-115">Child Elements</span></span>  
 <span data-ttu-id="8991a-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8991a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8991a-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8991a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8991a-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="8991a-118">Element</span></span>|<span data-ttu-id="8991a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8991a-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="8991a-120">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="8991a-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8991a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="8991a-121">Example</span></span>  
 <span data-ttu-id="8991a-122">В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="8991a-122">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="8991a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8991a-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="8991a-124">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="8991a-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
