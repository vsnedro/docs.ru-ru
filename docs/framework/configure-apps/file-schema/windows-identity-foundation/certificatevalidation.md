---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 583fef7eb364c39890b3f9304770b383c1ea6d2a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183511"
---
# \<certificateValidation>

<span data-ttu-id="adcf3-101">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="adcf3-101">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="adcf3-102">Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="adcf3-102">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a><span data-ttu-id="adcf3-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adcf3-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adcf3-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="adcf3-104">Attributes and Elements</span></span>  

 <span data-ttu-id="adcf3-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="adcf3-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adcf3-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="adcf3-106">Attributes</span></span>  
  
|<span data-ttu-id="adcf3-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="adcf3-107">Attribute</span></span>|<span data-ttu-id="adcf3-108">Описание</span><span class="sxs-lookup"><span data-stu-id="adcf3-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="adcf3-109">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="adcf3-109">certificateValidationMode</span></span>|<span data-ttu-id="adcf3-110"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Значение типа, указывающее режим проверки, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="adcf3-110">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="adcf3-111">Значение по умолчанию — "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="adcf3-111">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="adcf3-112">Чтобы указать настраиваемый проверяющий элемент управления, установите для этого атрибута значение "Custom" и укажите проверяющий элемент управления с помощью [\<certificateValidator>](certificatevalidator.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="adcf3-112">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="adcf3-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="adcf3-113">Optional.</span></span>|  
|<span data-ttu-id="adcf3-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="adcf3-114">revocationMode</span></span>|<span data-ttu-id="adcf3-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Значение типа, указывающее режим отзыва, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="adcf3-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="adcf3-116">Значение по умолчанию — "Online".</span><span class="sxs-lookup"><span data-stu-id="adcf3-116">The default value is "Online".</span></span> <span data-ttu-id="adcf3-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="adcf3-117">Optional.</span></span>|  
|<span data-ttu-id="adcf3-118">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="adcf3-118">trustedStoreLocation</span></span>|<span data-ttu-id="adcf3-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Значение типа, указывающее хранилище сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="adcf3-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="adcf3-120">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="adcf3-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="adcf3-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="adcf3-121">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="adcf3-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="adcf3-122">Child Elements</span></span>  
  
|<span data-ttu-id="adcf3-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="adcf3-123">Element</span></span>|<span data-ttu-id="adcf3-124">Описание</span><span class="sxs-lookup"><span data-stu-id="adcf3-124">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|<span data-ttu-id="adcf3-125">Указывает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="adcf3-125">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="adcf3-126">Этот тип используется только в том случае, если `certificateValidationMode` атрибут [\<certificateValidation>](certificatevalidation.md) элемента имеет значение Custom.</span><span class="sxs-lookup"><span data-stu-id="adcf3-126">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="adcf3-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="adcf3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="adcf3-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="adcf3-128">Element</span></span>|<span data-ttu-id="adcf3-129">Описание</span><span class="sxs-lookup"><span data-stu-id="adcf3-129">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="adcf3-130">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="adcf3-130">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="adcf3-131">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="adcf3-131">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adcf3-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="adcf3-132">Remarks</span></span>  

 <span data-ttu-id="adcf3-133">`<certificateValidation>`Элемент можно указать на уровне службы в `<identityConfiguration>` элементе или на уровне коллекции обработчика маркеров безопасности под `<securityTokenHandlerConfiguration>` элементом.</span><span class="sxs-lookup"><span data-stu-id="adcf3-133">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="adcf3-134">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="adcf3-134">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="adcf3-135">Некоторые обработчики маркеров позволяют указать параметры проверки сертификата в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="adcf3-135">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="adcf3-136">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны как на уровне службы, так и в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="adcf3-136">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adcf3-137">Пример</span><span class="sxs-lookup"><span data-stu-id="adcf3-137">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
