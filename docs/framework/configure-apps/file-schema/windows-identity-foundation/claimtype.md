---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252068"
---
# \<claimType>
<span data-ttu-id="fa8cb-101">Указывает одно необязательное или обязательное утверждение для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="fa8cb-101">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="fa8cb-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa8cb-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa8cb-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fa8cb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="fa8cb-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fa8cb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa8cb-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fa8cb-105">Attributes</span></span>  
  
|<span data-ttu-id="fa8cb-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fa8cb-106">Attribute</span></span>|<span data-ttu-id="fa8cb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fa8cb-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa8cb-108">type</span><span class="sxs-lookup"><span data-stu-id="fa8cb-108">type</span></span>|<span data-ttu-id="fa8cb-109">Тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="fa8cb-109">The claim type.</span></span> <span data-ttu-id="fa8cb-110">Обычно это URI.</span><span class="sxs-lookup"><span data-stu-id="fa8cb-110">Typically a URI.</span></span> <span data-ttu-id="fa8cb-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fa8cb-111">Required.</span></span>|  
|<span data-ttu-id="fa8cb-112">необязательный</span><span class="sxs-lookup"><span data-stu-id="fa8cb-112">optional</span></span>|<span data-ttu-id="fa8cb-113">Логическое значение, указывающее, является ли тип утверждения необязательным.</span><span class="sxs-lookup"><span data-stu-id="fa8cb-113">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="fa8cb-114">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="fa8cb-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa8cb-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fa8cb-115">Child Elements</span></span>  
 <span data-ttu-id="fa8cb-116">Нет</span><span class="sxs-lookup"><span data-stu-id="fa8cb-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa8cb-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fa8cb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fa8cb-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa8cb-118">Element</span></span>|<span data-ttu-id="fa8cb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fa8cb-119">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="fa8cb-120">Указывает набор обязательных утверждений для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="fa8cb-120">Specifies the set of required claims for incoming security tokens.</span></span>|
