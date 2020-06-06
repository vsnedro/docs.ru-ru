---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251941"
---
# \<nameClaimType>
<span data-ttu-id="47164-101">Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="47164-101">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="47164-102">Тип утверждения используется для поиска <xref:System.Security.Claims.Claim> в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом этого обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="47164-102">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="47164-103">Затем значение соответствующего утверждения задается в качестве имени объекта, <xref:System.Security.Principal.IIdentity> созданного из этого обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="47164-103">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="47164-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47164-104">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47164-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="47164-105">Attributes and Elements</span></span>  
 <span data-ttu-id="47164-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="47164-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47164-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="47164-107">Attributes</span></span>  
  
|<span data-ttu-id="47164-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="47164-108">Attribute</span></span>|<span data-ttu-id="47164-109">Описание</span><span class="sxs-lookup"><span data-stu-id="47164-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47164-110">value</span><span class="sxs-lookup"><span data-stu-id="47164-110">value</span></span>|<span data-ttu-id="47164-111">Строка, указывающая URI, который представляет тип утверждения для утверждения, используемого для <xref:System.Security.Principal.IIdentity.Name%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="47164-111">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="47164-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="47164-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47164-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="47164-113">Child Elements</span></span>  
 <span data-ttu-id="47164-114">Нет</span><span class="sxs-lookup"><span data-stu-id="47164-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47164-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="47164-115">Parent Elements</span></span>  
  
|<span data-ttu-id="47164-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="47164-116">Element</span></span>|<span data-ttu-id="47164-117">Описание</span><span class="sxs-lookup"><span data-stu-id="47164-117">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="47164-118">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="47164-118">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47164-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="47164-119">Remarks</span></span>  
 <span data-ttu-id="47164-120">`<nameClaimType>`Элемент задает <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> свойство при <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="47164-120">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47164-121">Пример</span><span class="sxs-lookup"><span data-stu-id="47164-121">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47164-122">См. также</span><span class="sxs-lookup"><span data-stu-id="47164-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
