---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252164"
---
# \<caches>
<span data-ttu-id="d35c4-101">Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="d35c4-101">Registers the caches used for session tokens and token replay detection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a><span data-ttu-id="d35c4-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d35c4-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d35c4-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d35c4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d35c4-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d35c4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d35c4-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d35c4-105">Attributes</span></span>  
 <span data-ttu-id="d35c4-106">Нет</span><span class="sxs-lookup"><span data-stu-id="d35c4-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d35c4-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d35c4-107">Child Elements</span></span>  
  
|<span data-ttu-id="d35c4-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="d35c4-108">Element</span></span>|<span data-ttu-id="d35c4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d35c4-109">Description</span></span>|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|<span data-ttu-id="d35c4-110">Регистрирует кэш для токенов сеанса с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d35c4-110">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[\<tokenReplayCache>](tokenreplaycache.md)|<span data-ttu-id="d35c4-111">Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d35c4-111">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d35c4-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d35c4-112">Parent Elements</span></span>  
  
|<span data-ttu-id="d35c4-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d35c4-113">Element</span></span>|<span data-ttu-id="d35c4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d35c4-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="d35c4-115">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="d35c4-115">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d35c4-116">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d35c4-116">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d35c4-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="d35c4-117">Remarks</span></span>  
 <span data-ttu-id="d35c4-118">`<caches>`Элемент можно указать на уровне службы в `<identityConfiguration>` элементе или на уровне коллекции обработчика маркеров безопасности под `<securityTokenHandlerConfiguration>` элементом.</span><span class="sxs-lookup"><span data-stu-id="d35c4-118">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="d35c4-119">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="d35c4-119">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="d35c4-120">`<caches>`Элемент представлен <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> классом.</span><span class="sxs-lookup"><span data-stu-id="d35c4-120">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="d35c4-121">Настроенные кэши представлены <xref:System.IdentityModel.Configuration.IdentityModelCaches> классом.</span><span class="sxs-lookup"><span data-stu-id="d35c4-121">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d35c4-122">Пример</span><span class="sxs-lookup"><span data-stu-id="d35c4-122">Example</span></span>  
 <span data-ttu-id="d35c4-123">В следующем коде XML показана конфигурация пользовательского кэша для хранения маркеров безопасности сеанса ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="d35c4-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="d35c4-124">Конфигурация берется из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="d35c4-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
