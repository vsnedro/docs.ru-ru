---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 9e099b8de486631702548b8a035a46a7e0f4eb30
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158478"
---
# \<claimsAuthenticationManager>

<span data-ttu-id="17d14-101">Регистрирует диспетчер проверки подлинности утверждений для входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="17d14-101">Registers a claims authentication manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="17d14-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17d14-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17d14-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="17d14-103">Attributes and Elements</span></span>  

 <span data-ttu-id="17d14-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="17d14-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17d14-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="17d14-105">Attributes</span></span>  
  
|<span data-ttu-id="17d14-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="17d14-106">Attribute</span></span>|<span data-ttu-id="17d14-107">Описание</span><span class="sxs-lookup"><span data-stu-id="17d14-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17d14-108">type</span><span class="sxs-lookup"><span data-stu-id="17d14-108">type</span></span>|<span data-ttu-id="17d14-109">Указывает пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса.</span><span class="sxs-lookup"><span data-stu-id="17d14-109">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="17d14-110">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="17d14-110">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17d14-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="17d14-111">Child Elements</span></span>  

 <span data-ttu-id="17d14-112">Если `type` атрибут отсутствует или `type` атрибут ссылается на <xref:System.Security.Claims.ClaimsAuthenticationManager> класс, `<claimsAuthenticationManager>` элемент не принимает дочерние элементы, однако классы, производные от, <xref:System.Security.Claims.ClaimsAuthenticationManager> могут определять дочерние элементы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="17d14-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17d14-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="17d14-113">Parent Elements</span></span>  
  
|<span data-ttu-id="17d14-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="17d14-114">Element</span></span>|<span data-ttu-id="17d14-115">Описание</span><span class="sxs-lookup"><span data-stu-id="17d14-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="17d14-116">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="17d14-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17d14-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="17d14-117">Remarks</span></span>  

 <span data-ttu-id="17d14-118">Поведение по умолчанию, предоставляемое <xref:System.Security.Claims.ClaimsAuthenticationManager> классом, отображает входящие утверждения.</span><span class="sxs-lookup"><span data-stu-id="17d14-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="17d14-119">Если `type` атрибут не указан или `type` атрибут указывает <xref:System.Security.Claims.ClaimsAuthenticationManager> класс, `<claimsAuthenticationManager>` элемент не принимает дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="17d14-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="17d14-120">Можно указать `type` атрибут для регистрации типа, производного от класса, <xref:System.Security.Claims.ClaimsAuthenticationManager> для реализации пользовательского поведения.</span><span class="sxs-lookup"><span data-stu-id="17d14-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="17d14-121">Производные классы могут поддерживать конфигурацию через дочерние элементы `<claimsAuthenticationManager>` элемента путем переопределения <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> метода для работы с этими элементами.</span><span class="sxs-lookup"><span data-stu-id="17d14-121">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="17d14-122">Схема, определенная для дочерних элементов, находится в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="17d14-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="17d14-123">`<claimsAuthenticationManager>`Элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="17d14-123">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17d14-124">Пример</span><span class="sxs-lookup"><span data-stu-id="17d14-124">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
