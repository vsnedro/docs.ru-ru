---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855149"
---
# \<identity>
<span data-ttu-id="117b0-101">Элемент identity позволяет разработчику клиента указать во время разработки ожидаемое удостоверение службы.</span><span class="sxs-lookup"><span data-stu-id="117b0-101">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="117b0-102">В процессе подтверждения между клиентом и службой инфраструктура Windows Communication Foundation (WCF) обеспечит соответствие идентификатора ожидаемой службы значениям этого элемента и, таким образом, может пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="117b0-102">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="117b0-103">Дополнительные сведения см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="117b0-103">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a><span data-ttu-id="117b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="117b0-104">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="117b0-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="117b0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="117b0-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="117b0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="117b0-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="117b0-107">Attributes</span></span>  
 <span data-ttu-id="117b0-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="117b0-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="117b0-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="117b0-109">Child Elements</span></span>  
  
|<span data-ttu-id="117b0-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="117b0-110">Element</span></span>|<span data-ttu-id="117b0-111">Описание</span><span class="sxs-lookup"><span data-stu-id="117b0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="117b0-112">сертификат</span><span class="sxs-lookup"><span data-stu-id="117b0-112">certificate</span></span>|<span data-ttu-id="117b0-113">Задает параметры сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="117b0-113">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="117b0-114">Это элемент типа <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="117b0-114">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="117b0-115">Он содержит атрибут `encodedValue`, являющийся строкой, указывающей значение, зашифрованное с помощью этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="117b0-115">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="117b0-116">certificateReference</span><span class="sxs-lookup"><span data-stu-id="117b0-116">certificateReference</span></span>|<span data-ttu-id="117b0-117">Задает параметры для проверки сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="117b0-117">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="117b0-118">Это элемент типа <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="117b0-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="117b0-119">dns</span><span class="sxs-lookup"><span data-stu-id="117b0-119">dns</span></span>|<span data-ttu-id="117b0-120">Задает службу DNS-сертификата X.509, используемого для проверки подлинности службы.</span><span class="sxs-lookup"><span data-stu-id="117b0-120">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="117b0-121">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.</span><span class="sxs-lookup"><span data-stu-id="117b0-121">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="117b0-122">rsa</span><span class="sxs-lookup"><span data-stu-id="117b0-122">rsa</span></span>|<span data-ttu-id="117b0-123">Задает значение поля RSA сертификата X.509, используемое для проверки подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="117b0-123">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="117b0-124">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.</span><span class="sxs-lookup"><span data-stu-id="117b0-124">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="117b0-125">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="117b0-125">servicePrincipalName</span></span>|<span data-ttu-id="117b0-126">Задает удостоверение имени участника-сервера, являющегося именем участника, используемым клиентом для уникальной идентификации экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="117b0-126">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="117b0-127">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.</span><span class="sxs-lookup"><span data-stu-id="117b0-127">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="117b0-128">Это элемент типа <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="117b0-128">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="117b0-129">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="117b0-129">userPrincipalName</span></span>|<span data-ttu-id="117b0-130">Задает удостоверение имени участника-пользователя, являющегося именем входа пользователя в сеть.</span><span class="sxs-lookup"><span data-stu-id="117b0-130">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="117b0-131">Имя участника-пользователя состоит из имени объекта пользователя, используемого в Active Directory, за которым следует символ ( \@ ) и, как правило, родительский домен системы доменных имен.</span><span class="sxs-lookup"><span data-stu-id="117b0-131">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="117b0-132">Например, Джефф в дереве доменов Fabrikam.com может иметь имя участника-пользователя [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) .</span><span class="sxs-lookup"><span data-stu-id="117b0-132">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="117b0-133">Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.</span><span class="sxs-lookup"><span data-stu-id="117b0-133">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="117b0-134">Это элемент типа <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="117b0-134">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="117b0-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="117b0-135">Parent Elements</span></span>  
  
|<span data-ttu-id="117b0-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="117b0-136">Element</span></span>|<span data-ttu-id="117b0-137">Описание</span><span class="sxs-lookup"><span data-stu-id="117b0-137">Description</span></span>|  
|-------------|-----------------|  
|[\<custom>](custom.md)|<span data-ttu-id="117b0-138">Задает настраиваемый одноранговый распознаватель для netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="117b0-138">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="117b0-139">Настраивает конечные точки службы.</span><span class="sxs-lookup"><span data-stu-id="117b0-139">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="117b0-140">\<endpoint>окна\<client></span><span class="sxs-lookup"><span data-stu-id="117b0-140">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="117b0-141">Настраивает конечные точки канала.</span><span class="sxs-lookup"><span data-stu-id="117b0-141">Configures channel endpoints.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="117b0-142">Задает службу маркеров безопасности для федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="117b0-142">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="117b0-143">Задает конечную точку метаданных для службы маркеров безопасности федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="117b0-143">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="117b0-144">Задает параметры для выданного маркера в настраиваемой привязке.</span><span class="sxs-lookup"><span data-stu-id="117b0-144">Defines parameters for an issued token in a custom binding.</span></span>|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="117b0-145">Задает локальную службу маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="117b0-145">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="117b0-146">См. также</span><span class="sxs-lookup"><span data-stu-id="117b0-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="117b0-147">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="117b0-147">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="117b0-148">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="117b0-148">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
