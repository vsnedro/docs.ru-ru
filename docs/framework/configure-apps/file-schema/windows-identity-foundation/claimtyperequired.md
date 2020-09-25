---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: a86265ba3963ebc8bea880befbcf80345529116d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203856"
---
# \<claimTypeRequired>

<span data-ttu-id="a4937-101">Указывает набор обязательных утверждений для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="a4937-101">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="a4937-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4937-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4937-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4937-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a4937-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4937-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4937-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4937-105">Attributes</span></span>  

 <span data-ttu-id="a4937-106">Нет</span><span class="sxs-lookup"><span data-stu-id="a4937-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4937-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4937-107">Child Elements</span></span>  
  
|<span data-ttu-id="a4937-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4937-108">Element</span></span>|<span data-ttu-id="a4937-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a4937-109">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="a4937-110">Указывает одно необязательное или обязательное утверждение для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="a4937-110">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4937-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4937-111">Parent Elements</span></span>  
  
|<span data-ttu-id="a4937-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4937-112">Element</span></span>|<span data-ttu-id="a4937-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a4937-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="a4937-114">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="a4937-114">Specifies service-level identity settings.</span></span>|
