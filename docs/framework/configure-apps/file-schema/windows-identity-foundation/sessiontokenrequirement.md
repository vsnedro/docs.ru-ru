---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152545"
---
# \<sessionTokenRequirement>
<span data-ttu-id="108d0-101">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="108d0-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="108d0-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="108d0-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="108d0-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="108d0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="108d0-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="108d0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="108d0-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="108d0-105">Attributes</span></span>  
  
|<span data-ttu-id="108d0-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="108d0-106">Attribute</span></span>|<span data-ttu-id="108d0-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="108d0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="108d0-108">lifetime</span><span class="sxs-lookup"><span data-stu-id="108d0-108">lifetime</span></span>|<span data-ttu-id="108d0-109">Указывает время существования маркеров сеанса.</span><span class="sxs-lookup"><span data-stu-id="108d0-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="108d0-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="108d0-110">Child Elements</span></span>  
 <span data-ttu-id="108d0-111">Нет</span><span class="sxs-lookup"><span data-stu-id="108d0-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="108d0-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="108d0-112">Parent Elements</span></span>  
  
|<span data-ttu-id="108d0-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="108d0-113">Element</span></span>|<span data-ttu-id="108d0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="108d0-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="108d0-115">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="108d0-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="108d0-116">Пример</span><span class="sxs-lookup"><span data-stu-id="108d0-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
