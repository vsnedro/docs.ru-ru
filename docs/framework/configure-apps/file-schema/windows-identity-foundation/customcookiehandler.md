---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a8ee23ac6facaea18cd7f1820616cb9b16afa336
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189855"
---
# \<customCookieHandler>

<span data-ttu-id="18220-101">Задает тип обработчика пользовательских файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="18220-101">Sets the custom cookie handler type.</span></span> <span data-ttu-id="18220-102">Этот элемент может присутствовать только в том случае, если `mode` атрибут `<cookieHandler>` элемента имеет значение Custom.</span><span class="sxs-lookup"><span data-stu-id="18220-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="18220-103">Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="18220-103">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="18220-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18220-104">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18220-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18220-105">Attributes and Elements</span></span>  

 <span data-ttu-id="18220-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18220-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18220-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18220-107">Attributes</span></span>  
  
|<span data-ttu-id="18220-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18220-108">Attribute</span></span>|<span data-ttu-id="18220-109">Описание</span><span class="sxs-lookup"><span data-stu-id="18220-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18220-110">type</span><span class="sxs-lookup"><span data-stu-id="18220-110">type</span></span>|<span data-ttu-id="18220-111">Указывает пользовательский тип, производный от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="18220-111">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="18220-112">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="18220-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18220-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18220-113">Child Elements</span></span>  

 <span data-ttu-id="18220-114">Нет</span><span class="sxs-lookup"><span data-stu-id="18220-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18220-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18220-115">Parent Elements</span></span>  
  
|<span data-ttu-id="18220-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="18220-116">Element</span></span>|<span data-ttu-id="18220-117">Описание</span><span class="sxs-lookup"><span data-stu-id="18220-117">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="18220-118">Настраивает <xref:System.IdentityModel.Services.CookieHandler> , что <xref:System.IdentityModel.Services.SessionAuthenticationModule> использует для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="18220-118">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18220-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="18220-119">Remarks</span></span>  

 <span data-ttu-id="18220-120">При указании пользовательского обработчика файлов cookie путем присвоения `mode` атрибуту `<cookieHandler>` элемента значения "Custom" необходимо указать тип пользовательского обработчика файлов cookie, добавив `<customCookieHandler>` дочерний элемент, ссылающийся на тип обработчика файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="18220-120">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="18220-121">Этот элемент не может быть указан, если `mode` для атрибута задано значение "фрагментированный" или "по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="18220-121">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="18220-122">Пользовательские обработчики файлов cookie должны быть производными от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="18220-122">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="18220-123">`<customCookieHandler>`Элемент представлен <xref:System.IdentityModel.Configuration.CustomTypeElement> классом.</span><span class="sxs-lookup"><span data-stu-id="18220-123">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18220-124">Пример</span><span class="sxs-lookup"><span data-stu-id="18220-124">Example</span></span>  

 <span data-ttu-id="18220-125">В следующем примере SAM настраивается для использования пользовательского обработчика файлов cookie типа `MyNamespace.MyCustomCookieHandler` .</span><span class="sxs-lookup"><span data-stu-id="18220-125">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18220-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="18220-126">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
