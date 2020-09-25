---
title: Элемент <appDomainResourceMonitoring>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 9ecf2e382b5d483377df871835793219b3f74760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170276"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="0d8fa-102">Элемент \<appDomainResourceMonitoring></span><span class="sxs-lookup"><span data-stu-id="0d8fa-102">\<appDomainResourceMonitoring> Element</span></span>

<span data-ttu-id="0d8fa-103">Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="0d8fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d8fa-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d8fa-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0d8fa-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0d8fa-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d8fa-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0d8fa-107">Attributes</span></span>  
  
|<span data-ttu-id="0d8fa-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0d8fa-108">Attribute</span></span>|<span data-ttu-id="0d8fa-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0d8fa-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0d8fa-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="0d8fa-111">Указывает, собирает ли среда выполнения статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0d8fa-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="0d8fa-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="0d8fa-113">Значение</span><span class="sxs-lookup"><span data-stu-id="0d8fa-113">Value</span></span>|<span data-ttu-id="0d8fa-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0d8fa-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="0d8fa-115">Собираются статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="0d8fa-116">Статистика по мониторингу ресурсов домена приложений не собирается.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d8fa-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0d8fa-117">Child Elements</span></span>  

 <span data-ttu-id="0d8fa-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d8fa-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0d8fa-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0d8fa-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d8fa-120">Element</span></span>|<span data-ttu-id="0d8fa-121">Описание</span><span class="sxs-lookup"><span data-stu-id="0d8fa-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0d8fa-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0d8fa-123">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d8fa-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d8fa-124">Remarks</span></span>  

 <span data-ttu-id="0d8fa-125">Мониторинг ресурсов домена приложений доступен через класс домена управляемого приложения, интерфейс размещения [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) и трассировку событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="0d8fa-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="0d8fa-126">При включении мониторинга статистика собирается для всех доменов приложений в процессе в течение жизненного цикла процесса.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="0d8fa-127">Чтобы включить мониторинг из управляемого кода, используйте <xref:System.AppDomain.MonitoringIsEnabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="0d8fa-128">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d8fa-129">Пример</span><span class="sxs-lookup"><span data-stu-id="0d8fa-129">Example</span></span>  

 <span data-ttu-id="0d8fa-130">В следующем примере показано, как включить отслеживание ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0d8fa-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d8fa-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0d8fa-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0d8fa-132">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0d8fa-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0d8fa-133">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="0d8fa-133">Configuration File Schema</span></span>](../index.md)
