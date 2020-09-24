---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 9e92bbcacf529a97e1ae936e93e38c98eab19cab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157269"
---
# \<issuer>

<span data-ttu-id="af9f8-101">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="af9f8-101">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="af9f8-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af9f8-102">Syntax</span></span>  
  
```xml  
<issuer address="Uri">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af9f8-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="af9f8-103">Attributes and Elements</span></span>  

 <span data-ttu-id="af9f8-104">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="af9f8-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af9f8-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="af9f8-105">Attributes</span></span>  
  
|<span data-ttu-id="af9f8-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="af9f8-106">Attribute</span></span>|<span data-ttu-id="af9f8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="af9f8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af9f8-108">address</span><span class="sxs-lookup"><span data-stu-id="af9f8-108">address</span></span>|<span data-ttu-id="af9f8-109">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="af9f8-109">Required string.</span></span> <span data-ttu-id="af9f8-110">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="af9f8-110">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af9f8-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="af9f8-111">Child Elements</span></span>  
  
|<span data-ttu-id="af9f8-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="af9f8-112">Element</span></span>|<span data-ttu-id="af9f8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="af9f8-113">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="af9f8-114">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="af9f8-114">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="af9f8-115">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="af9f8-115">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af9f8-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="af9f8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="af9f8-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="af9f8-117">Element</span></span>|<span data-ttu-id="af9f8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="af9f8-118">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="af9f8-119">Определяет параметры безопасности на уровне сообщений для [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="af9f8-119">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af9f8-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="af9f8-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="af9f8-121">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="af9f8-121">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="af9f8-122">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="af9f8-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="af9f8-123">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="af9f8-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="af9f8-124">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="af9f8-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="af9f8-125">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="af9f8-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="af9f8-126">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="af9f8-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
