---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: d892fbd802ed366ca7af9b85fbf5c23d4d27e0f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157009"
---
# \<securityTokenHandlers>

<span data-ttu-id="21c62-101">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="21c62-101">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
## <a name="syntax"></a><span data-ttu-id="21c62-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21c62-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21c62-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="21c62-103">Attributes and Elements</span></span>  

 <span data-ttu-id="21c62-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="21c62-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21c62-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="21c62-105">Attributes</span></span>  
  
|<span data-ttu-id="21c62-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="21c62-106">Attribute</span></span>|<span data-ttu-id="21c62-107">Описание</span><span class="sxs-lookup"><span data-stu-id="21c62-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21c62-108">name</span><span class="sxs-lookup"><span data-stu-id="21c62-108">name</span></span>|<span data-ttu-id="21c62-109">Указывает имя коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="21c62-109">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="21c62-110">Платформа принимает только те значения, которые распознаются платформой: "ActAs" и "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="21c62-110">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="21c62-111">Если коллекции обработчиков маркеров указаны с одним из этих имен, коллекция будет использоваться при обработке маркеров ActAs или OnBehalfOf соответственно.</span><span class="sxs-lookup"><span data-stu-id="21c62-111">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21c62-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="21c62-112">Child Elements</span></span>  
  
|<span data-ttu-id="21c62-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="21c62-113">Element</span></span>|<span data-ttu-id="21c62-114">Описание</span><span class="sxs-lookup"><span data-stu-id="21c62-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="21c62-115">Добавляет обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="21c62-115">Adds a security token handler to the token handler collection.</span></span>|  
|[\<clear>](clear.md)|<span data-ttu-id="21c62-116">Удаляет все обработчики маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="21c62-116">Clears all security token handlers from the token handler collection.</span></span>|  
|[\<remove>](remove.md)|<span data-ttu-id="21c62-117">Удаляет обработчик маркера безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="21c62-117">Removes a security token handler from the token handler collection.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="21c62-118">Предоставляет конфигурацию для коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="21c62-118">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21c62-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="21c62-119">Parent Elements</span></span>  
  
|<span data-ttu-id="21c62-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="21c62-120">Element</span></span>|<span data-ttu-id="21c62-121">Описание</span><span class="sxs-lookup"><span data-stu-id="21c62-121">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="21c62-122">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="21c62-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21c62-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="21c62-123">Remarks</span></span>  

 <span data-ttu-id="21c62-124">В конфигурации службы можно указать одну или несколько именованных коллекций обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="21c62-124">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="21c62-125">Имя коллекции можно указать с помощью `name` атрибута.</span><span class="sxs-lookup"><span data-stu-id="21c62-125">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="21c62-126">Единственными именами, которые обрабатывает платформа, являются "ActAs" и "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="21c62-126">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="21c62-127">Если в этих коллекциях есть обработчики, они используются службой маркеров безопасности (STS) вместо обработчиков по умолчанию при обработке `ActAs` и `OnBehalfOf` токенах.</span><span class="sxs-lookup"><span data-stu-id="21c62-127">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="21c62-128">По умолчанию коллекция заполняется следующими типами обработчиков: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ,,,, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> и <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="21c62-128">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="21c62-129">Коллекцию можно изменить с помощью `<add>` `<remove>` элементов, и `<clear>` .</span><span class="sxs-lookup"><span data-stu-id="21c62-129">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="21c62-130">Необходимо убедиться, что в коллекции существует только один обработчик любого определенного типа.</span><span class="sxs-lookup"><span data-stu-id="21c62-130">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="21c62-131">Например, если создать производный обработчик от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, то либо обработчик, либо <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> может быть настроен в одной коллекции, но не в обоих.</span><span class="sxs-lookup"><span data-stu-id="21c62-131">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="21c62-132">Используйте `<securityTokenHandlerConfiguration>` элемент, чтобы указать параметры конфигурации для обработчиков в коллекции.</span><span class="sxs-lookup"><span data-stu-id="21c62-132">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="21c62-133">Параметры, заданные с помощью этого элемента, переопределяют указанные в службе элементы с помощью [\<identityConfiguration>](identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="21c62-133">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="21c62-134">Некоторые обработчики (включая несколько встроенных типов обработчиков) могут поддерживать дополнительную конфигурацию через дочерний элемент `<add>` элемента.</span><span class="sxs-lookup"><span data-stu-id="21c62-134">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="21c62-135">Параметры, заданные для обработчика, переопределяют эквивалентные параметры, указанные в коллекции или службе.</span><span class="sxs-lookup"><span data-stu-id="21c62-135">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
