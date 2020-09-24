---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e909756a58d5008d917fca84af0e478fc4878d2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156814"
---
# \<system.identityModel.services>

<span data-ttu-id="7bf4c-102">Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-102">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
## <a name="syntax"></a><span data-ttu-id="7bf4c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bf4c-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bf4c-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7bf4c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="7bf4c-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bf4c-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7bf4c-106">Attributes</span></span>  

 <span data-ttu-id="7bf4c-107">Нет</span><span class="sxs-lookup"><span data-stu-id="7bf4c-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7bf4c-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7bf4c-108">Child Elements</span></span>  
  
|<span data-ttu-id="7bf4c-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="7bf4c-109">Element</span></span>|<span data-ttu-id="7bf4c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7bf4c-110">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="7bf4c-111">Содержит параметры, которые настраивают <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> HTTP-модули (SAM).</span><span class="sxs-lookup"><span data-stu-id="7bf4c-111">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7bf4c-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7bf4c-112">Parent Elements</span></span>  

 <span data-ttu-id="7bf4c-113">None</span><span class="sxs-lookup"><span data-stu-id="7bf4c-113">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bf4c-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="7bf4c-114">Remarks</span></span>  

 <span data-ttu-id="7bf4c-115">Добавьте `<system.identityModel.services>` раздел в файл конфигурации приложения, чтобы указать параметры для SAM и всфам.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-115">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7bf4c-116">При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде Диспетчер авторизации утверждений ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) и политика, используемые для принятия решений об авторизации, настраиваются с помощью `<identityConfiguration>` элемента, который неявно или явно упоминается в `<federationConfiguration>` элементе в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-116">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="7bf4c-117">Дополнительные сведения см. в разделе **Примечания** в [\<federationConfiguration>](federationconfiguration.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-117">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="7bf4c-118">`<system.identityModel.services>`Раздел представлен <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> классом.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-118">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="7bf4c-119">Коллекция дочерних элементов, `<federationConfiguration>` настроенных в разделе, представлена <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> классом.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-119">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bf4c-120">Пример</span><span class="sxs-lookup"><span data-stu-id="7bf4c-120">Example</span></span>  

 <span data-ttu-id="7bf4c-121">В следующем коде XML показано, как добавить `<system.identityModel.services>` раздел в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-121">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="7bf4c-122">Сначала необходимо добавить объявления разделов как для `<system.identityModel.services>` раздела, так и для `<system.identityModel>` разделов.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-122">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="7bf4c-123">(При добавлении раздела необходимо `<system.identityModel.services>` также добавить объявление для `<system.identityModel>` раздела, чтобы гарантировать, что при необходимости раздел по умолчанию `<identityConfiguration>` может быть создан средой выполнения.) После добавления объявлений разделов можно настроить параметры федеративной проверки подлинности в `<system.identityModel.services>` элементе.</span><span class="sxs-lookup"><span data-stu-id="7bf4c-123">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"
        issuer="http://localhost:15839/wsFederationSTS/Issue"
        realm="http://localhost:50969/" reply="http://localhost:50969/"
        requireHttps="false"
        signOutReply="http://localhost:50969/SignedOutPage.html"
        signOutQueryString="Param1=value2&Param2=value2"
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
