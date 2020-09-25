---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 10a6d2aaad7d63d00b3a57032d0d218f756454d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175958"
---
# \<issuerMetadata>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="d9c24-101">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9c24-101">Syntax</span></span>  
  
```xml  
<issuerMetadata address="String">
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
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9c24-102">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d9c24-102">Attributes and Elements</span></span>  

 <span data-ttu-id="d9c24-103">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d9c24-103">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9c24-104">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d9c24-104">Attributes</span></span>  
  
|<span data-ttu-id="d9c24-105">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d9c24-105">Attribute</span></span>|<span data-ttu-id="d9c24-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d9c24-106">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9c24-107">address</span><span class="sxs-lookup"><span data-stu-id="d9c24-107">address</span></span>|<span data-ttu-id="d9c24-108">Обязательный атрибут элемента `string`.</span><span class="sxs-lookup"><span data-stu-id="d9c24-108">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="d9c24-109">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d9c24-109">Specifies the address of the endpoint.</span></span> <span data-ttu-id="d9c24-110">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="d9c24-110">The address must be an absolute URI.</span></span> <span data-ttu-id="d9c24-111">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="d9c24-111">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9c24-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d9c24-112">Child Elements</span></span>  
  
|<span data-ttu-id="d9c24-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9c24-113">Element</span></span>|<span data-ttu-id="d9c24-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d9c24-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="d9c24-115">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="d9c24-115">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="d9c24-116">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d9c24-116">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9c24-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d9c24-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d9c24-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9c24-118">Element</span></span>|<span data-ttu-id="d9c24-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d9c24-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="d9c24-120">Определяет параметры безопасности на уровне сообщений для [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="d9c24-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9c24-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d9c24-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="d9c24-122">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="d9c24-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d9c24-123">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="d9c24-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d9c24-124">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="d9c24-124">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d9c24-125">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="d9c24-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
