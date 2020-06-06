---
title: <certificate> для <identity>;
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850014"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="2a70a-102">\<certificate> для \<identity>;</span><span class="sxs-lookup"><span data-stu-id="2a70a-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="2a70a-103">Задает сертификат X.509, используемый для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="2a70a-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="2a70a-104">Дополнительные сведения о задании значения элемента см. в разделе [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2a70a-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="2a70a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a70a-105">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a70a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2a70a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2a70a-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2a70a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a70a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2a70a-108">Attributes</span></span>  
  
|<span data-ttu-id="2a70a-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2a70a-109">Attribute</span></span>|<span data-ttu-id="2a70a-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="2a70a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a70a-111">encodedValue</span><span class="sxs-lookup"><span data-stu-id="2a70a-111">encodedValue</span></span>|<span data-ttu-id="2a70a-112">Кодировка Base64 сертификата.</span><span class="sxs-lookup"><span data-stu-id="2a70a-112">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a70a-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2a70a-113">Child Elements</span></span>  
 <span data-ttu-id="2a70a-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2a70a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a70a-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2a70a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2a70a-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a70a-116">Element</span></span>|<span data-ttu-id="2a70a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2a70a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="2a70a-118">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="2a70a-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2a70a-119">Пример</span><span class="sxs-lookup"><span data-stu-id="2a70a-119">Example</span></span>  
 <span data-ttu-id="2a70a-120">В следующем коде задается кодированное представление сертификата, используемого для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="2a70a-120">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="2a70a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2a70a-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="2a70a-122">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="2a70a-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
