---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399710"
---
# \<serviceAuthenticationManager>
<span data-ttu-id="dfa13-101">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="dfa13-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="dfa13-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfa13-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfa13-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dfa13-103">Attributes and Elements</span></span>  
 <span data-ttu-id="dfa13-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dfa13-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfa13-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dfa13-105">Attributes</span></span>  
  
|<span data-ttu-id="dfa13-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dfa13-106">Attribute</span></span>|<span data-ttu-id="dfa13-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="dfa13-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dfa13-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="dfa13-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="dfa13-109">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="dfa13-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfa13-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dfa13-110">Child Elements</span></span>  
 <span data-ttu-id="dfa13-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dfa13-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfa13-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dfa13-112">Parent Elements</span></span>  
  
|<span data-ttu-id="dfa13-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="dfa13-113">Element</span></span>|<span data-ttu-id="dfa13-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dfa13-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="dfa13-115">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="dfa13-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfa13-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dfa13-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
