---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 3ea9684245bd1c1c3b9ce171a045fff49d0ba592
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156918"
---
# \<serviceTokenResolver>

<span data-ttu-id="470df-101">Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="470df-101">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="470df-102">Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="470df-102">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="470df-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="470df-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="470df-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="470df-104">Attributes and Elements</span></span>  

 <span data-ttu-id="470df-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="470df-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="470df-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="470df-106">Attributes</span></span>  
  
|<span data-ttu-id="470df-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="470df-107">Attribute</span></span>|<span data-ttu-id="470df-108">Описание</span><span class="sxs-lookup"><span data-stu-id="470df-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="470df-109">type</span><span class="sxs-lookup"><span data-stu-id="470df-109">type</span></span>|<span data-ttu-id="470df-110">Указывает тип сопоставителя токенов службы.</span><span class="sxs-lookup"><span data-stu-id="470df-110">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="470df-111">Либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> тип, либо тип, производный от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="470df-111">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="470df-112">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="470df-112">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="470df-113">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="470df-113">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="470df-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="470df-114">Child Elements</span></span>  

 <span data-ttu-id="470df-115">Нет</span><span class="sxs-lookup"><span data-stu-id="470df-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="470df-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="470df-116">Parent Elements</span></span>  
  
|<span data-ttu-id="470df-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="470df-117">Element</span></span>|<span data-ttu-id="470df-118">Описание</span><span class="sxs-lookup"><span data-stu-id="470df-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="470df-119">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="470df-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="470df-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="470df-120">Remarks</span></span>  

 <span data-ttu-id="470df-121">Сопоставитель токенов службы можно использовать для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="470df-121">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="470df-122">Он используется для получения ключа, который должен использоваться для расшифровки входящих токенов.</span><span class="sxs-lookup"><span data-stu-id="470df-122">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="470df-123">Необходимо указать `type` атрибут.</span><span class="sxs-lookup"><span data-stu-id="470df-123">You must specify the `type` attribute.</span></span> <span data-ttu-id="470df-124">Указанный тип может быть либо либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> пользовательским типом, производным от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="470df-124">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="470df-125">Некоторые обработчики маркеров позволяют задавать параметры сопоставителя токенов служб в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="470df-125">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="470df-126">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="470df-126">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="470df-127">Указание `<serviceTokenResolver>` элемента в качестве дочернего элемента [\<identityConfiguration>](identityconfiguration.md) элемента является устаревшим, но по-прежнему поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="470df-127">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="470df-128">Параметры `<securityTokenHandlerConfiguration>` элемента переопределяют их для `<identityConfiguration>` элемента.</span><span class="sxs-lookup"><span data-stu-id="470df-128">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="470df-129">Пример</span><span class="sxs-lookup"><span data-stu-id="470df-129">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
