---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397915"
---
# \<issuer>
<span data-ttu-id="0af7d-101">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="0af7d-101">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="0af7d-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0af7d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0af7d-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0af7d-103">Attributes and Elements</span></span>  
 <span data-ttu-id="0af7d-104">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0af7d-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0af7d-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0af7d-105">Attributes</span></span>  
  
|<span data-ttu-id="0af7d-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0af7d-106">Attribute</span></span>|<span data-ttu-id="0af7d-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0af7d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0af7d-108">address</span><span class="sxs-lookup"><span data-stu-id="0af7d-108">address</span></span>|<span data-ttu-id="0af7d-109">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="0af7d-109">Required string.</span></span> <span data-ttu-id="0af7d-110">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="0af7d-110">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0af7d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0af7d-111">Child Elements</span></span>  
  
|<span data-ttu-id="0af7d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="0af7d-112">Element</span></span>|<span data-ttu-id="0af7d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0af7d-113">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="0af7d-114">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="0af7d-114">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="0af7d-115">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="0af7d-115">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0af7d-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0af7d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0af7d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="0af7d-117">Element</span></span>|<span data-ttu-id="0af7d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0af7d-118">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="0af7d-119">Определяет параметры безопасности на уровне сообщений для [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="0af7d-119">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0af7d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0af7d-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="0af7d-121">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="0af7d-121">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0af7d-122">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="0af7d-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0af7d-123">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="0af7d-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0af7d-124">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="0af7d-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0af7d-125">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="0af7d-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="0af7d-126">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="0af7d-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
