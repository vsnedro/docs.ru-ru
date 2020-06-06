---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152636"
---
# \<samlSecurityTokenRequirement>
<span data-ttu-id="509d9-101">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="509d9-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="509d9-102">Представляется <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом.</span><span class="sxs-lookup"><span data-stu-id="509d9-102">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="509d9-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="509d9-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="509d9-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="509d9-104">Attributes and Elements</span></span>  
 <span data-ttu-id="509d9-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="509d9-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="509d9-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="509d9-106">Attributes</span></span>  
  
|<span data-ttu-id="509d9-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="509d9-107">Attribute</span></span>|<span data-ttu-id="509d9-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="509d9-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="509d9-109">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="509d9-109">mapToWindows</span></span>|<span data-ttu-id="509d9-110">Указывает, должен ли обработчик маркера сопоставлять проверяющий токен с учетной записью Windows, используя входящее утверждение имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="509d9-110">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="509d9-111">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="509d9-111">The default is "false".</span></span>|  
|<span data-ttu-id="509d9-112">иссуерцертификатеревокатионмоде</span><span class="sxs-lookup"><span data-stu-id="509d9-112">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="509d9-113"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Значение типа, указывающее режим отзыва, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="509d9-113">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="509d9-114">Значение по умолчанию — "Online".</span><span class="sxs-lookup"><span data-stu-id="509d9-114">The default value is "Online".</span></span>|  
|<span data-ttu-id="509d9-115">иссуерцертификатевалидатионмоде</span><span class="sxs-lookup"><span data-stu-id="509d9-115">issuerCertificateValidationMode</span></span>|<span data-ttu-id="509d9-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Значение типа, указывающее режим проверки, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="509d9-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="509d9-117">Значение по умолчанию — "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="509d9-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="509d9-118">иссуерцертификатетрустедсторелокатион</span><span class="sxs-lookup"><span data-stu-id="509d9-118">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="509d9-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Значение типа, указывающее хранилище сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="509d9-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="509d9-120">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="509d9-120">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="509d9-121">иссуерцертификатевалидатор</span><span class="sxs-lookup"><span data-stu-id="509d9-121">issuerCertificateValidator</span></span>|<span data-ttu-id="509d9-122">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="509d9-122">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="509d9-123">Если `issuerCertificateValidationMode` атрибут имеет значение Custom, для проверки сертификата издателя используется экземпляр этого типа.</span><span class="sxs-lookup"><span data-stu-id="509d9-123">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="509d9-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="509d9-124">Child Elements</span></span>  
  
|<span data-ttu-id="509d9-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="509d9-125">Element</span></span>|<span data-ttu-id="509d9-126">Описание</span><span class="sxs-lookup"><span data-stu-id="509d9-126">Description</span></span>|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|<span data-ttu-id="509d9-127">Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="509d9-127">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[\<roleClaimType>](roleclaimtype.md)|<span data-ttu-id="509d9-128">Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="509d9-128">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="509d9-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="509d9-129">Parent Elements</span></span>  
  
|<span data-ttu-id="509d9-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="509d9-130">Element</span></span>|<span data-ttu-id="509d9-131">Описание</span><span class="sxs-lookup"><span data-stu-id="509d9-131">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="509d9-132">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="509d9-132">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="509d9-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="509d9-133">Remarks</span></span>  
 <span data-ttu-id="509d9-134">`<samlSecurityTokenRequirement>`Элемент представлен <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом в объектной модели и используется для настройки `SamlSecurityTokenRequirement` свойства в <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> или <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="509d9-134">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="509d9-135">Пример</span><span class="sxs-lookup"><span data-stu-id="509d9-135">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
