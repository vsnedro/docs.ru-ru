---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 7c2b6bdc62da63905d7ff33a9984808e7b7d114f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544544"
---
# \<add>
<span data-ttu-id="4eae6-101">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="4eae6-101">Adds the specified security token handler to the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="4eae6-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4eae6-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4eae6-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4eae6-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4eae6-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4eae6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4eae6-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4eae6-105">Attributes</span></span>  
  
|<span data-ttu-id="4eae6-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4eae6-106">Attribute</span></span>|<span data-ttu-id="4eae6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4eae6-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4eae6-108">type</span><span class="sxs-lookup"><span data-stu-id="4eae6-108">type</span></span>|<span data-ttu-id="4eae6-109">Имя типа CLR обработчика токенов, который необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="4eae6-109">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="4eae6-110">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="4eae6-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4eae6-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4eae6-111">Child Elements</span></span>  
  
|<span data-ttu-id="4eae6-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="4eae6-112">Element</span></span>|<span data-ttu-id="4eae6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4eae6-113">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="4eae6-114">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="4eae6-114">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|<span data-ttu-id="4eae6-115">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="4eae6-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="4eae6-116">Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="4eae6-116">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="4eae6-117">Предоставляет необязательную конфигурацию для <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="4eae6-117">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4eae6-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4eae6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4eae6-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="4eae6-119">Element</span></span>|<span data-ttu-id="4eae6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="4eae6-120">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="4eae6-121">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="4eae6-121">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4eae6-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="4eae6-122">Remarks</span></span>  
 <span data-ttu-id="4eae6-123">`<add>`Элемент может принимать один дочерний элемент, указывающий конфигурацию для обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="4eae6-123">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="4eae6-124">Это зависит от того, поддерживает ли эта функция класс обработчика, на который ссылается `type` атрибут `<add>` элемента.</span><span class="sxs-lookup"><span data-stu-id="4eae6-124">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="4eae6-125">Классы обработчиков маркеров, которые предоставляют эту функцию, должны предоставлять конструктор, принимающий <xref:System.Xml.XmlElement> объект.</span><span class="sxs-lookup"><span data-stu-id="4eae6-125">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="4eae6-126">Некоторые из встроенных классов обработчиков маркеров безопасности предоставляют эту функцию.</span><span class="sxs-lookup"><span data-stu-id="4eae6-126">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="4eae6-127">Эти классы: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> ,,, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> и <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="4eae6-127">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4eae6-128">Коллекция обработчиков маркеров может содержать только один обработчик любого заданного типа.</span><span class="sxs-lookup"><span data-stu-id="4eae6-128">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="4eae6-129">Это означает, например, что если требуется добавить обработчик, производный от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, в коллекцию, необходимо сначала удалить объект <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , который существует по умолчанию, из коллекции.</span><span class="sxs-lookup"><span data-stu-id="4eae6-129">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="4eae6-130">С помощью элемента можно [\<remove>](remove.md) удалить один обработчик из коллекции или использовать [\<clear>](clear.md) элемент для удаления всех обработчиков из коллекции.</span><span class="sxs-lookup"><span data-stu-id="4eae6-130">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="4eae6-131">Параметры, заданные для обработчика, переопределяют эквивалентные параметры, заданные в коллекции обработчика маркеров в [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) элементе, и те, которые указаны на уровне службы в [\<identityConfiguration>](identityconfiguration.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="4eae6-131">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eae6-132">Пример</span><span class="sxs-lookup"><span data-stu-id="4eae6-132">Example</span></span>  
 <span data-ttu-id="4eae6-133">В следующем коде XML показано использование `<add>` `<remove>` элементов и для замены обработчика токена сеанса по умолчанию обработчиком пользовательского маркера сеанса.</span><span class="sxs-lookup"><span data-stu-id="4eae6-133">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="4eae6-134">XML взят из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="4eae6-134">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
