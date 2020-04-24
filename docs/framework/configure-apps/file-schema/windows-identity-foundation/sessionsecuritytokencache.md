---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646069"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="075e6-101">\<sessionsecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="075e6-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="075e6-102">Регистрирует кэш для маркеров сеанса с помощью службы или коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="075e6-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="075e6-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="075e6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="075e6-104">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="075e6-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="075e6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="075e6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="075e6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<кэши>**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="075e6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="075e6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionsecurityTokenCache>**</span><span class="sxs-lookup"><span data-stu-id="075e6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="075e6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="075e6-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="075e6-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="075e6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="075e6-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="075e6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="075e6-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="075e6-111">Attributes</span></span>  
  
|<span data-ttu-id="075e6-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="075e6-112">Attribute</span></span>|<span data-ttu-id="075e6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="075e6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="075e6-114">type</span><span class="sxs-lookup"><span data-stu-id="075e6-114">type</span></span>|<span data-ttu-id="075e6-115">Тип, который вытекает <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> из класса.</span><span class="sxs-lookup"><span data-stu-id="075e6-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="075e6-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="075e6-116">Child Elements</span></span>  
 <span data-ttu-id="075e6-117">None</span><span class="sxs-lookup"><span data-stu-id="075e6-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="075e6-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="075e6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="075e6-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="075e6-119">Element</span></span>|<span data-ttu-id="075e6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="075e6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="075e6-121">\<кэши></span><span class="sxs-lookup"><span data-stu-id="075e6-121">\<caches></span></span>](caches.md)|<span data-ttu-id="075e6-122">Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="075e6-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="075e6-123">Пример</span><span class="sxs-lookup"><span data-stu-id="075e6-123">Example</span></span>  
 <span data-ttu-id="075e6-124">Следующие XML показывает конфигурацию пользовательского кэша для<xref:System.IdentityModel.Tokens.SessionSecurityToken>хранения маркеров безопасности сеанса ().</span><span class="sxs-lookup"><span data-stu-id="075e6-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="075e6-125">Конфигурация взята `ClaimsAwareWebFarm` из образца.</span><span class="sxs-lookup"><span data-stu-id="075e6-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="075e6-126">Для получения дополнительной информации [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index)об этой выборке см.</span><span class="sxs-lookup"><span data-stu-id="075e6-126">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="075e6-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="075e6-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
