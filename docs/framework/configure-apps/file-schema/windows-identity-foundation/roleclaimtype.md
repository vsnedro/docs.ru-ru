---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251915"
---
# \<roleClaimType>
<span data-ttu-id="914ea-101">Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="914ea-101">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="914ea-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="914ea-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="914ea-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="914ea-103">Attributes and Elements</span></span>  
 <span data-ttu-id="914ea-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="914ea-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="914ea-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="914ea-105">Attributes</span></span>  
  
|<span data-ttu-id="914ea-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="914ea-106">Attribute</span></span>|<span data-ttu-id="914ea-107">Описание</span><span class="sxs-lookup"><span data-stu-id="914ea-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="914ea-108">value</span><span class="sxs-lookup"><span data-stu-id="914ea-108">value</span></span>|<span data-ttu-id="914ea-109">Строка, указывающая URI, который представляет тип утверждения, используемого для типа утверждения роли.</span><span class="sxs-lookup"><span data-stu-id="914ea-109">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="914ea-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="914ea-110">Child Elements</span></span>  
 <span data-ttu-id="914ea-111">Нет</span><span class="sxs-lookup"><span data-stu-id="914ea-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="914ea-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="914ea-112">Parent Elements</span></span>  
  
|<span data-ttu-id="914ea-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="914ea-113">Element</span></span>|<span data-ttu-id="914ea-114">Описание</span><span class="sxs-lookup"><span data-stu-id="914ea-114">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="914ea-115">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="914ea-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="914ea-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="914ea-116">Remarks</span></span>  
 <span data-ttu-id="914ea-117">`<roleClaimType>`Элемент задает <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> свойство при <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> инициализации объекта из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="914ea-117">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="914ea-118">Пример</span><span class="sxs-lookup"><span data-stu-id="914ea-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="914ea-119">См. также</span><span class="sxs-lookup"><span data-stu-id="914ea-119">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
