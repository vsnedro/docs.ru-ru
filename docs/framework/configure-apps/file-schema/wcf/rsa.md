---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 1698ce421b4dcefc6ab94206443d2d7bca47aca8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162287"
---
# \<rsa>

<span data-ttu-id="fa963-101">Защищенный клиент WCF, подключающийся к конечной точке с использованием этого удостоверения, проверяет, что среди утверждений, представленных сервером, есть утверждение, содержащее открытый ключ RSA, который используется для конструирования этого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="fa963-101">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**  
  
## <a name="syntax"></a><span data-ttu-id="fa963-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa963-102">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa963-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fa963-103">Attributes and Elements</span></span>  

 <span data-ttu-id="fa963-104">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fa963-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa963-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fa963-105">Attributes</span></span>  
  
|<span data-ttu-id="fa963-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fa963-106">Attribute</span></span>|<span data-ttu-id="fa963-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fa963-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa963-108">value</span><span class="sxs-lookup"><span data-stu-id="fa963-108">value</span></span>|<span data-ttu-id="fa963-109">Дополнительная строка.</span><span class="sxs-lookup"><span data-stu-id="fa963-109">Optional String.</span></span> <span data-ttu-id="fa963-110">Значение открытого ключа RSA, с которым происходит сравнение на клиенте.</span><span class="sxs-lookup"><span data-stu-id="fa963-110">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa963-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fa963-111">Child Elements</span></span>  

 <span data-ttu-id="fa963-112">Нет</span><span class="sxs-lookup"><span data-stu-id="fa963-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa963-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fa963-113">Parent Elements</span></span>  
  
|<span data-ttu-id="fa963-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa963-114">Element</span></span>|<span data-ttu-id="fa963-115">Описание</span><span class="sxs-lookup"><span data-stu-id="fa963-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="fa963-116">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="fa963-116">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa963-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa963-117">Remarks</span></span>  

 <span data-ttu-id="fa963-118">Проверка RSA дает возможность ограничить проверку подлинности, задействовав один сертификат с использованием его ключа RSA или другого значения ключа RSA, созданного в отдельном порядке.</span><span class="sxs-lookup"><span data-stu-id="fa963-118">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="fa963-119">Это позволяет выполнить более строгую проверку подлинности конкретного ключа RSA, однако если значение ключа RSA будет изменено, служба больше не будет работать с существующими клиентами.</span><span class="sxs-lookup"><span data-stu-id="fa963-119">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="fa963-120">Дополнительные сведения об использовании удостоверения для проверки службы для клиента см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="fa963-120">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa963-121">Пример</span><span class="sxs-lookup"><span data-stu-id="fa963-121">Example</span></span>  

 <span data-ttu-id="fa963-122">В следующем коде конфигурации задается значение открытого ключа сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="fa963-122">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="fa963-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fa963-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="fa963-124">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="fa963-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
