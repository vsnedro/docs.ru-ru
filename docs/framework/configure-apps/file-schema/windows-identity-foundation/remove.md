---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: c4ba7b6f2a9b9092c5f24d424c6de2b0f510ac88
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165004"
---
# \<remove>

<span data-ttu-id="d20d2-101">Удаляет указанный обработчик маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="d20d2-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="d20d2-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d20d2-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d20d2-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d20d2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d20d2-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d20d2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d20d2-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d20d2-105">Attributes</span></span>  
  
|<span data-ttu-id="d20d2-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d20d2-106">Attribute</span></span>|<span data-ttu-id="d20d2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d20d2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d20d2-108">type</span><span class="sxs-lookup"><span data-stu-id="d20d2-108">type</span></span>|<span data-ttu-id="d20d2-109">Имя типа CLR удаляемого обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="d20d2-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="d20d2-110">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="d20d2-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="d20d2-111">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d20d2-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d20d2-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d20d2-112">Child Elements</span></span>  

 <span data-ttu-id="d20d2-113">Нет</span><span class="sxs-lookup"><span data-stu-id="d20d2-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d20d2-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d20d2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d20d2-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d20d2-115">Element</span></span>|<span data-ttu-id="d20d2-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d20d2-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="d20d2-117">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="d20d2-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d20d2-118">Пример</span><span class="sxs-lookup"><span data-stu-id="d20d2-118">Example</span></span>  

 <span data-ttu-id="d20d2-119">В следующем коде XML показано использование `<add>` `<remove>` элементов и для замены обработчика токена сеанса по умолчанию обработчиком пользовательского маркера сеанса.</span><span class="sxs-lookup"><span data-stu-id="d20d2-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="d20d2-120">XML взят из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="d20d2-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
