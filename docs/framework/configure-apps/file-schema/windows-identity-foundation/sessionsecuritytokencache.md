---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 347d1a1cba95bbd4992de95d6617e8828f4fc374
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156905"
---
# \<sessionSecurityTokenCache>

<span data-ttu-id="c0604-101">Регистрирует кэш для токенов сеанса с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="c0604-101">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a><span data-ttu-id="c0604-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0604-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0604-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c0604-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c0604-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c0604-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0604-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0604-105">Attributes</span></span>  
  
|<span data-ttu-id="c0604-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c0604-106">Attribute</span></span>|<span data-ttu-id="c0604-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c0604-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0604-108">type</span><span class="sxs-lookup"><span data-stu-id="c0604-108">type</span></span>|<span data-ttu-id="c0604-109">Тип, производный от <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> класса.</span><span class="sxs-lookup"><span data-stu-id="c0604-109">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0604-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c0604-110">Child Elements</span></span>  

 <span data-ttu-id="c0604-111">Нет</span><span class="sxs-lookup"><span data-stu-id="c0604-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0604-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c0604-112">Parent Elements</span></span>  
  
|<span data-ttu-id="c0604-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0604-113">Element</span></span>|<span data-ttu-id="c0604-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c0604-114">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="c0604-115">Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="c0604-115">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c0604-116">Пример</span><span class="sxs-lookup"><span data-stu-id="c0604-116">Example</span></span>  

 <span data-ttu-id="c0604-117">В следующем коде XML показана конфигурация пользовательского кэша для хранения маркеров безопасности сеанса ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="c0604-117">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="c0604-118">Конфигурация берется из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="c0604-118">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="c0604-119">Дополнительные сведения об этом образце см. в разделе [Индекс образца кода WIF](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span><span class="sxs-lookup"><span data-stu-id="c0604-119">For more information about this sample, see [WIF Code Sample Index](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0604-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0604-120">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
