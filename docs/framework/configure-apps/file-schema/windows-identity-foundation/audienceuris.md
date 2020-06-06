---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252171"
---
# \<audienceUris>
<span data-ttu-id="d3da8-101">Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="d3da8-101">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="d3da8-102">Маркеры не будут приниматься, если они не относятся к одному из разрешенных URI аудитории.</span><span class="sxs-lookup"><span data-stu-id="d3da8-102">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="d3da8-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3da8-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3da8-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d3da8-104">Attributes and Elements</span></span>  
 <span data-ttu-id="d3da8-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d3da8-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3da8-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3da8-106">Attributes</span></span>  
  
|<span data-ttu-id="d3da8-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d3da8-107">Attribute</span></span>|<span data-ttu-id="d3da8-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="d3da8-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3da8-109">mode</span><span class="sxs-lookup"><span data-stu-id="d3da8-109">mode</span></span>|<span data-ttu-id="d3da8-110"><xref:System.IdentityModel.Selectors.AudienceUriMode>Значение типа, указывающее, следует ли применять ограничение аудитории к входящему токену.</span><span class="sxs-lookup"><span data-stu-id="d3da8-110">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="d3da8-111">Возможные значения: "всегда", "Never" и "Беареркэйонли".</span><span class="sxs-lookup"><span data-stu-id="d3da8-111">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="d3da8-112">Значение по умолчанию — Always.</span><span class="sxs-lookup"><span data-stu-id="d3da8-112">The default is "Always".</span></span> <span data-ttu-id="d3da8-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="d3da8-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3da8-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d3da8-114">Child Elements</span></span>  
  
|<span data-ttu-id="d3da8-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3da8-115">Element</span></span>|<span data-ttu-id="d3da8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d3da8-116">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="d3da8-117">Добавляет URI, указанный `value` атрибутом, в коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="d3da8-117">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="d3da8-118">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d3da8-118">The `value` attribute is required.</span></span> <span data-ttu-id="d3da8-119">В URI учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="d3da8-119">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="d3da8-120">Очищает коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="d3da8-120">Clears the audienceUris collection.</span></span> <span data-ttu-id="d3da8-121">Все идентификаторы удаляются из коллекции.</span><span class="sxs-lookup"><span data-stu-id="d3da8-121">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="d3da8-122">Удаляет URI, указанный `value` атрибутом из коллекции audienceUris.</span><span class="sxs-lookup"><span data-stu-id="d3da8-122">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="d3da8-123">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d3da8-123">The `value` attribute is required.</span></span> <span data-ttu-id="d3da8-124">В URI учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="d3da8-124">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3da8-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d3da8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d3da8-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3da8-126">Element</span></span>|<span data-ttu-id="d3da8-127">Описание</span><span class="sxs-lookup"><span data-stu-id="d3da8-127">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d3da8-128">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d3da8-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3da8-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3da8-129">Remarks</span></span>  
 <span data-ttu-id="d3da8-130">По умолчанию коллекция пуста; Используйте `<add>` `<clear>` элементы, и `<remove>` для изменения коллекции.</span><span class="sxs-lookup"><span data-stu-id="d3da8-130">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="d3da8-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler><xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>объекты и используют значения в коллекции URI аудитории для настройки любых допустимых ограничений URI аудитории в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектах.</span><span class="sxs-lookup"><span data-stu-id="d3da8-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="d3da8-132">`<audienceUris>`Элемент представлен <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> классом.</span><span class="sxs-lookup"><span data-stu-id="d3da8-132">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="d3da8-133">Отдельный URI, добавленный в коллекцию, представлен <xref:System.IdentityModel.Configuration.AudienceUriElement> классом.</span><span class="sxs-lookup"><span data-stu-id="d3da8-133">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3da8-134">Использование `<audienceUris>` элемента в качестве дочернего элемента [\<identityConfiguration>](identityconfiguration.md) элемента является устаревшим, но по-прежнему поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="d3da8-134">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d3da8-135">Параметры `<securityTokenHandlerConfiguration>` элемента переопределяют их для `<identityConfiguration>` элемента.</span><span class="sxs-lookup"><span data-stu-id="d3da8-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3da8-136">Пример</span><span class="sxs-lookup"><span data-stu-id="d3da8-136">Example</span></span>  
 <span data-ttu-id="d3da8-137">В следующем коде XML показано, как настроить допустимые URI аудитории для приложения.</span><span class="sxs-lookup"><span data-stu-id="d3da8-137">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="d3da8-138">В этом примере настраивается один универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="d3da8-138">This example configures a single URI.</span></span> <span data-ttu-id="d3da8-139">Маркеры, областью которых является этот URI, будут приняты, все остальные будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="d3da8-139">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
