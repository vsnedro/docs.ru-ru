---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 1b5427210142c70c31c5f736c9b5e281dca53f33
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150873"
---
# \<claimType>

<span data-ttu-id="997b4-101">Указывает одно необязательное или обязательное утверждение для входящих токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="997b4-101">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="997b4-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="997b4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="997b4-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="997b4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="997b4-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="997b4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="997b4-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="997b4-105">Attributes</span></span>  
  
|<span data-ttu-id="997b4-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="997b4-106">Attribute</span></span>|<span data-ttu-id="997b4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="997b4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="997b4-108">type</span><span class="sxs-lookup"><span data-stu-id="997b4-108">type</span></span>|<span data-ttu-id="997b4-109">Тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="997b4-109">The claim type.</span></span> <span data-ttu-id="997b4-110">Обычно это URI.</span><span class="sxs-lookup"><span data-stu-id="997b4-110">Typically a URI.</span></span> <span data-ttu-id="997b4-111">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="997b4-111">Required.</span></span>|  
|<span data-ttu-id="997b4-112">необязательный</span><span class="sxs-lookup"><span data-stu-id="997b4-112">optional</span></span>|<span data-ttu-id="997b4-113">Логическое значение, указывающее, является ли тип утверждения необязательным.</span><span class="sxs-lookup"><span data-stu-id="997b4-113">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="997b4-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="997b4-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="997b4-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="997b4-115">Child Elements</span></span>  

 <span data-ttu-id="997b4-116">Нет</span><span class="sxs-lookup"><span data-stu-id="997b4-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="997b4-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="997b4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="997b4-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="997b4-118">Element</span></span>|<span data-ttu-id="997b4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="997b4-119">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="997b4-120">Указывает набор обязательных утверждений для входящих маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="997b4-120">Specifies the set of required claims for incoming security tokens.</span></span>|
