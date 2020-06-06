---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251739"
---
# \<userNameSecurityTokenHandlerRequirement>
<span data-ttu-id="32e49-101">Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="32e49-101">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="32e49-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32e49-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32e49-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="32e49-103">Attributes and Elements</span></span>  
 <span data-ttu-id="32e49-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="32e49-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32e49-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32e49-105">Attributes</span></span>  
  
|<span data-ttu-id="32e49-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="32e49-106">Attribute</span></span>|<span data-ttu-id="32e49-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="32e49-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32e49-108">мембершиппровидернаме</span><span class="sxs-lookup"><span data-stu-id="32e49-108">membershipProviderName</span></span>|<span data-ttu-id="32e49-109">Указывает <xref:System.Web.Security.MembershipProvider> , который должен использоваться обработчиком маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="32e49-109">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32e49-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32e49-110">Child Elements</span></span>  
 <span data-ttu-id="32e49-111">Нет</span><span class="sxs-lookup"><span data-stu-id="32e49-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32e49-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="32e49-112">Parent Elements</span></span>  
  
|<span data-ttu-id="32e49-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="32e49-113">Element</span></span>|<span data-ttu-id="32e49-114">Описание</span><span class="sxs-lookup"><span data-stu-id="32e49-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="32e49-115">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="32e49-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32e49-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="32e49-116">Remarks</span></span>  
 <span data-ttu-id="32e49-117">`<userNameSecurityTokenHandlerRequirement>`Элемент задает <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> свойство при <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> инициализации объекта из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="32e49-117">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32e49-118">Пример</span><span class="sxs-lookup"><span data-stu-id="32e49-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
