---
title: Элемент <performanceCounters> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 584bdafbbd60303401cbc6ad96b8654fe11c7077
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756264"
---
# <a name="performancecounters-element-network-settings"></a><span data-ttu-id="6c379-102">Элемент \<performanceCounters> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="6c379-102">\<performanceCounters> Element (Network Settings)</span></span>

<span data-ttu-id="6c379-103">Включает или отключает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="6c379-103">Enables or disables networking performance counters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**

## <a name="syntax"></a><span data-ttu-id="6c379-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c379-104">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c379-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c379-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6c379-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6c379-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c379-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c379-107">Attributes</span></span>  
  
|<span data-ttu-id="6c379-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6c379-108">Attribute</span></span>|<span data-ttu-id="6c379-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6c379-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6c379-110">Указывает, включены ли счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="6c379-110">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="6c379-111">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="6c379-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c379-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c379-112">Child Elements</span></span>  

 <span data-ttu-id="6c379-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6c379-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c379-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c379-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6c379-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c379-115">Element</span></span>|<span data-ttu-id="6c379-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6c379-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c379-117">параметры</span><span class="sxs-lookup"><span data-stu-id="6c379-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="6c379-118">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="6c379-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c379-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c379-119">Remarks</span></span>  

 <span data-ttu-id="6c379-120">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6c379-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="6c379-121">Счетчики производительности сети необходимо включить для использования в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6c379-121">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="6c379-122">Все счетчики производительности сети включаются и отключаются с помощью одного параметра в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6c379-122">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="6c379-123">Включить или отключить отдельные счетчики производительности сети невозможно.</span><span class="sxs-lookup"><span data-stu-id="6c379-123">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="6c379-124">Дополнительные сведения о конкретных счетчиках производительности сети см. в разделе [Сетевые счетчики производительности](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span><span class="sxs-lookup"><span data-stu-id="6c379-124">For more information on the specific networking performance counters, see [Networking performance counters](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span></span>  
  
 <span data-ttu-id="6c379-125">Значение по умолчанию — сетевые счетчики производительности отключены.</span><span class="sxs-lookup"><span data-stu-id="6c379-125">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="6c379-126"><xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>Свойство можно использовать для получения текущего значения атрибута **Enabled** из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6c379-126">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c379-127">Например, .</span><span class="sxs-lookup"><span data-stu-id="6c379-127">Example</span></span>  

 <span data-ttu-id="6c379-128">В следующем примере показано, как настроить <xref:System.Net> и связанные пространства имен для включения сетевых счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="6c379-128">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c379-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6c379-129">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6c379-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="6c379-130">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6c379-131">Счетчики производительности сети</span><span class="sxs-lookup"><span data-stu-id="6c379-131">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)
