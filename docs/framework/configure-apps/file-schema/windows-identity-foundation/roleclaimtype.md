---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 36d727f97597df816779da1c1f7ed5da1a1697f2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164939"
---
# \<roleClaimType>

<span data-ttu-id="94559-101">Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="94559-101">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="94559-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94559-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94559-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="94559-103">Attributes and Elements</span></span>  

 <span data-ttu-id="94559-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="94559-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94559-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="94559-105">Attributes</span></span>  
  
|<span data-ttu-id="94559-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="94559-106">Attribute</span></span>|<span data-ttu-id="94559-107">Описание</span><span class="sxs-lookup"><span data-stu-id="94559-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94559-108">value</span><span class="sxs-lookup"><span data-stu-id="94559-108">value</span></span>|<span data-ttu-id="94559-109">Строка, указывающая URI, который представляет тип утверждения, используемого для типа утверждения роли.</span><span class="sxs-lookup"><span data-stu-id="94559-109">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94559-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="94559-110">Child Elements</span></span>  

 <span data-ttu-id="94559-111">Нет</span><span class="sxs-lookup"><span data-stu-id="94559-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94559-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="94559-112">Parent Elements</span></span>  
  
|<span data-ttu-id="94559-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="94559-113">Element</span></span>|<span data-ttu-id="94559-114">Описание</span><span class="sxs-lookup"><span data-stu-id="94559-114">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="94559-115">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="94559-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94559-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="94559-116">Remarks</span></span>  

 <span data-ttu-id="94559-117">`<roleClaimType>`Элемент задает <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> свойство при <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="94559-117">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94559-118">Пример</span><span class="sxs-lookup"><span data-stu-id="94559-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="94559-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94559-119">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
