---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251925"
---
# \<remove>
<span data-ttu-id="e84be-101">Удаляет указанный обработчик маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e84be-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="e84be-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e84be-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e84be-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e84be-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e84be-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e84be-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e84be-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e84be-105">Attributes</span></span>  
  
|<span data-ttu-id="e84be-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e84be-106">Attribute</span></span>|<span data-ttu-id="e84be-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e84be-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e84be-108">type</span><span class="sxs-lookup"><span data-stu-id="e84be-108">type</span></span>|<span data-ttu-id="e84be-109">Имя типа CLR удаляемого обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="e84be-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="e84be-110">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="e84be-110">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="e84be-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e84be-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e84be-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e84be-112">Child Elements</span></span>  
 <span data-ttu-id="e84be-113">Нет</span><span class="sxs-lookup"><span data-stu-id="e84be-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e84be-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e84be-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e84be-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e84be-115">Element</span></span>|<span data-ttu-id="e84be-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e84be-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="e84be-117">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="e84be-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e84be-118">Пример</span><span class="sxs-lookup"><span data-stu-id="e84be-118">Example</span></span>  
 <span data-ttu-id="e84be-119">В следующем коде XML показано использование `<add>` `<remove>` элементов и для замены обработчика токена сеанса по умолчанию обработчиком пользовательского маркера сеанса.</span><span class="sxs-lookup"><span data-stu-id="e84be-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="e84be-120">XML взят из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="e84be-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
