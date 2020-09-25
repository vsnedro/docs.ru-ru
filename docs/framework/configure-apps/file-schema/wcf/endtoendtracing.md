---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b50c0c3db644787fe41ee58ced7eb640e7295f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190024"
---
# \<endToEndTracing>

<span data-ttu-id="ff4a1-101">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="ff4a1-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="ff4a1-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff4a1-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff4a1-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff4a1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ff4a1-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ff4a1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff4a1-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff4a1-105">Attributes</span></span>  
  
|<span data-ttu-id="ff4a1-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ff4a1-106">Attribute</span></span>|<span data-ttu-id="ff4a1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ff4a1-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="ff4a1-108">Логическое значение, указывающее, включено ли отслеживание действия.</span><span class="sxs-lookup"><span data-stu-id="ff4a1-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="ff4a1-109">Логическое значение, указывающее, включено ли отслеживание потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="ff4a1-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="ff4a1-110">Логическое значение, указывающее, задано ли атрибуту propagate значение true.</span><span class="sxs-lookup"><span data-stu-id="ff4a1-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff4a1-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff4a1-111">Child Elements</span></span>  

 <span data-ttu-id="ff4a1-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff4a1-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff4a1-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff4a1-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ff4a1-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff4a1-114">Element</span></span>|<span data-ttu-id="ff4a1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ff4a1-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="ff4a1-116">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="ff4a1-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff4a1-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff4a1-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="ff4a1-118">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="ff4a1-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
