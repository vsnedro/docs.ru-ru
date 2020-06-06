---
title: Элемент <appDomainResourceMonitoring>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154380"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="419eb-102">Элемент \<appDomainResourceMonitoring></span><span class="sxs-lookup"><span data-stu-id="419eb-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="419eb-103">Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.</span><span class="sxs-lookup"><span data-stu-id="419eb-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="419eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="419eb-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="419eb-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="419eb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="419eb-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="419eb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="419eb-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="419eb-107">Attributes</span></span>  
  
|<span data-ttu-id="419eb-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="419eb-108">Attribute</span></span>|<span data-ttu-id="419eb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="419eb-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="419eb-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="419eb-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="419eb-111">Указывает, собирает ли среда выполнения статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="419eb-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="419eb-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="419eb-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="419eb-113">Значение</span><span class="sxs-lookup"><span data-stu-id="419eb-113">Value</span></span>|<span data-ttu-id="419eb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="419eb-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="419eb-115">Собираются статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="419eb-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="419eb-116">Статистика по мониторингу ресурсов домена приложений не собирается.</span><span class="sxs-lookup"><span data-stu-id="419eb-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="419eb-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="419eb-117">Child Elements</span></span>  
 <span data-ttu-id="419eb-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="419eb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="419eb-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="419eb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="419eb-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="419eb-120">Element</span></span>|<span data-ttu-id="419eb-121">Описание</span><span class="sxs-lookup"><span data-stu-id="419eb-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="419eb-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="419eb-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="419eb-123">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="419eb-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="419eb-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="419eb-124">Remarks</span></span>  
 <span data-ttu-id="419eb-125">Мониторинг ресурсов домена приложений доступен через класс домена управляемого приложения, интерфейс размещения [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) и трассировку событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="419eb-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="419eb-126">При включении мониторинга статистика собирается для всех доменов приложений в процессе в течение жизненного цикла процесса.</span><span class="sxs-lookup"><span data-stu-id="419eb-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="419eb-127">Чтобы включить мониторинг из управляемого кода, используйте <xref:System.AppDomain.MonitoringIsEnabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="419eb-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="419eb-128">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="419eb-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="419eb-129">Пример</span><span class="sxs-lookup"><span data-stu-id="419eb-129">Example</span></span>  
 <span data-ttu-id="419eb-130">В следующем примере показано, как включить отслеживание ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="419eb-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="419eb-131">См. также</span><span class="sxs-lookup"><span data-stu-id="419eb-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="419eb-132">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="419eb-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="419eb-133">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="419eb-133">Configuration File Schema</span></span>](../index.md)
