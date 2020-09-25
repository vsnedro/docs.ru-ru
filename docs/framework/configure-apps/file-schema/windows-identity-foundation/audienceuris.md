---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: c9787d8e0d8d66494bbf2dbd0e24ff39178a4cde
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189907"
---
# \<audienceUris>

<span data-ttu-id="bdfaf-101">Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="bdfaf-101">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="bdfaf-102">Маркеры не будут приниматься, если они не относятся к одному из разрешенных URI аудитории.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-102">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="bdfaf-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdfaf-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdfaf-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bdfaf-104">Attributes and Elements</span></span>  

 <span data-ttu-id="bdfaf-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdfaf-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bdfaf-106">Attributes</span></span>  
  
|<span data-ttu-id="bdfaf-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bdfaf-107">Attribute</span></span>|<span data-ttu-id="bdfaf-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bdfaf-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdfaf-109">mode</span><span class="sxs-lookup"><span data-stu-id="bdfaf-109">mode</span></span>|<span data-ttu-id="bdfaf-110"><xref:System.IdentityModel.Selectors.AudienceUriMode>Значение типа, указывающее, следует ли применять ограничение аудитории к входящему токену.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-110">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="bdfaf-111">Возможные значения: "всегда", "Never" и "Беареркэйонли".</span><span class="sxs-lookup"><span data-stu-id="bdfaf-111">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="bdfaf-112">Значение по умолчанию — Always.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-112">The default is "Always".</span></span> <span data-ttu-id="bdfaf-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdfaf-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bdfaf-114">Child Elements</span></span>  
  
|<span data-ttu-id="bdfaf-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="bdfaf-115">Element</span></span>|<span data-ttu-id="bdfaf-116">Описание</span><span class="sxs-lookup"><span data-stu-id="bdfaf-116">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="bdfaf-117">Добавляет URI, указанный `value` атрибутом, в коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-117">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="bdfaf-118">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-118">The `value` attribute is required.</span></span> <span data-ttu-id="bdfaf-119">В URI учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-119">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="bdfaf-120">Очищает коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-120">Clears the audienceUris collection.</span></span> <span data-ttu-id="bdfaf-121">Все идентификаторы удаляются из коллекции.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-121">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="bdfaf-122">Удаляет URI, указанный `value` атрибутом из коллекции audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-122">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="bdfaf-123">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-123">The `value` attribute is required.</span></span> <span data-ttu-id="bdfaf-124">В URI учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-124">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bdfaf-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bdfaf-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bdfaf-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="bdfaf-126">Element</span></span>|<span data-ttu-id="bdfaf-127">Описание</span><span class="sxs-lookup"><span data-stu-id="bdfaf-127">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="bdfaf-128">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdfaf-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="bdfaf-129">Remarks</span></span>  

 <span data-ttu-id="bdfaf-130">По умолчанию коллекция пуста; Используйте `<add>` `<clear>` элементы, и `<remove>` для изменения коллекции.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-130">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="bdfaf-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler><xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>объекты и используют значения в коллекции URI аудитории для настройки любых допустимых ограничений URI аудитории в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектах.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="bdfaf-132">`<audienceUris>`Элемент представлен <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> классом.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-132">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="bdfaf-133">Отдельный URI, добавленный в коллекцию, представлен <xref:System.IdentityModel.Configuration.AudienceUriElement> классом.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-133">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bdfaf-134">Использование `<audienceUris>` элемента в качестве дочернего элемента [\<identityConfiguration>](identityconfiguration.md) элемента является устаревшим, но по-прежнему поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-134">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="bdfaf-135">Параметры `<securityTokenHandlerConfiguration>` элемента переопределяют их для `<identityConfiguration>` элемента.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdfaf-136">Пример</span><span class="sxs-lookup"><span data-stu-id="bdfaf-136">Example</span></span>  

 <span data-ttu-id="bdfaf-137">В следующем коде XML показано, как настроить допустимые URI аудитории для приложения.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-137">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="bdfaf-138">В этом примере настраивается один универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="bdfaf-138">This example configures a single URI.</span></span> <span data-ttu-id="bdfaf-139">Маркеры, областью которых является этот URI, будут приняты, все остальные будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="bdfaf-139">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
