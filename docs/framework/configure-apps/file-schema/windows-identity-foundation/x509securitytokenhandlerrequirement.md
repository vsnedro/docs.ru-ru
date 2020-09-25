---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: a6a8185297e1345de9fa20c7d4d0dffbdcd8620f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185396"
---
# \<x509SecurityTokenHandlerRequirement>

<span data-ttu-id="e8f27-101">Предоставляет необязательную конфигурацию для <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="e8f27-101">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="e8f27-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8f27-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8f27-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e8f27-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e8f27-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e8f27-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8f27-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e8f27-105">Attributes</span></span>  
  
|<span data-ttu-id="e8f27-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e8f27-106">Attribute</span></span>|<span data-ttu-id="e8f27-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e8f27-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8f27-108">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e8f27-108">certificateValidationMode</span></span>|<span data-ttu-id="e8f27-109"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Значение типа, указывающее режим проверки, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="e8f27-109">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e8f27-110">Значение по умолчанию — "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="e8f27-110">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="e8f27-111">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="e8f27-111">mapToWindows</span></span>|<span data-ttu-id="e8f27-112">Указывает, должен ли обработчик маркера сопоставлять проверяющий токен с учетной записью Windows, используя входящее утверждение имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="e8f27-112">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="e8f27-113">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="e8f27-113">The default is "false".</span></span>|  
|<span data-ttu-id="e8f27-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="e8f27-114">revocationMode</span></span>|<span data-ttu-id="e8f27-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Значение типа, указывающее режим отзыва, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="e8f27-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e8f27-116">Значение по умолчанию — "Online".</span><span class="sxs-lookup"><span data-stu-id="e8f27-116">The default value is "Online".</span></span>|  
|<span data-ttu-id="e8f27-117">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e8f27-117">trustedStoreLocation</span></span>|<span data-ttu-id="e8f27-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Значение типа, указывающее хранилище сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="e8f27-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="e8f27-119">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="e8f27-119">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="e8f27-120">цертификатевалидатор</span><span class="sxs-lookup"><span data-stu-id="e8f27-120">certificateValidator</span></span>|<span data-ttu-id="e8f27-121">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="e8f27-121">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="e8f27-122">Если `certificateValidationMode` атрибут имеет значение Custom, для проверки сертификата издателя используется экземпляр этого типа.</span><span class="sxs-lookup"><span data-stu-id="e8f27-122">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8f27-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e8f27-123">Child Elements</span></span>  

 <span data-ttu-id="e8f27-124">Нет</span><span class="sxs-lookup"><span data-stu-id="e8f27-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8f27-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e8f27-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e8f27-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="e8f27-126">Element</span></span>|<span data-ttu-id="e8f27-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e8f27-127">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="e8f27-128">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e8f27-128">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8f27-129">Пример</span><span class="sxs-lookup"><span data-stu-id="e8f27-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
