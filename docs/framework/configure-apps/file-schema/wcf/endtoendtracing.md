---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855298"
---
# \<endToEndTracing>
<span data-ttu-id="d2401-101">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="d2401-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="d2401-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2401-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2401-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d2401-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d2401-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d2401-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2401-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d2401-105">Attributes</span></span>  
  
|<span data-ttu-id="d2401-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d2401-106">Attribute</span></span>|<span data-ttu-id="d2401-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="d2401-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="d2401-108">Логическое значение, указывающее, включено ли отслеживание действия.</span><span class="sxs-lookup"><span data-stu-id="d2401-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="d2401-109">Логическое значение, указывающее, включено ли отслеживание потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="d2401-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="d2401-110">Логическое значение, указывающее, задано ли атрибуту propagate значение true.</span><span class="sxs-lookup"><span data-stu-id="d2401-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2401-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d2401-111">Child Elements</span></span>  
 <span data-ttu-id="d2401-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d2401-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2401-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d2401-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d2401-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="d2401-114">Element</span></span>|<span data-ttu-id="d2401-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d2401-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="d2401-116">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="d2401-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2401-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d2401-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="d2401-118">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="d2401-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
