---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: daf576488e38bed28c7c0e5222bc053659372ff0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184005"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="561db-102">Элемент \<relativeBindForResources></span><span class="sxs-lookup"><span data-stu-id="561db-102">\<relativeBindForResources> Element</span></span>

<span data-ttu-id="561db-103">Оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="561db-103">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="561db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="561db-104">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="561db-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="561db-105">Attributes and Elements</span></span>  

 <span data-ttu-id="561db-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="561db-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="561db-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="561db-107">Attributes</span></span>  
  
|<span data-ttu-id="561db-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="561db-108">Attribute</span></span>|<span data-ttu-id="561db-109">Описание</span><span class="sxs-lookup"><span data-stu-id="561db-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="561db-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="561db-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="561db-111">Указывает, оптимизирует ли среда CLR проверку на наличие вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="561db-111">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="561db-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="561db-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="561db-113">Значение</span><span class="sxs-lookup"><span data-stu-id="561db-113">Value</span></span>|<span data-ttu-id="561db-114">Описание</span><span class="sxs-lookup"><span data-stu-id="561db-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="561db-115">Среда выполнения не оптимизирует зонд для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="561db-115">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="561db-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="561db-116">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="561db-117">Среда выполнения оптимизирует зонд для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="561db-117">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="561db-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="561db-118">Child Elements</span></span>  

 <span data-ttu-id="561db-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="561db-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="561db-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="561db-120">Parent Elements</span></span>  
  
|<span data-ttu-id="561db-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="561db-121">Element</span></span>|<span data-ttu-id="561db-122">Описание</span><span class="sxs-lookup"><span data-stu-id="561db-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="561db-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="561db-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="561db-124">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="561db-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="561db-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="561db-125">Remarks</span></span>  

 <span data-ttu-id="561db-126">Как правило, диспетчер ресурсов зонды для ресурсов, как описано в разделе [Упаковка и развертывание ресурсов](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="561db-126">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="561db-127">Это означает, что при диспетчер ресурсов зондах для конкретной локализованной версии ресурса она может искать в глобальном кэше сборок, искать в папке, зависящей от языка и региональных параметров, в базе кода приложения, запрашивать установщик Windows для вспомогательных сборок и создавать <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="561db-127">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="561db-128">`<relativeBindForResources>`Элемент оптимизирует способ диспетчер ресурсов проверки для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="561db-128">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="561db-129">Это может повысить производительность при проверке ресурсов при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="561db-129">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="561db-130">При развертывании вспомогательной сборки в том же расположении, что и сборка кода.</span><span class="sxs-lookup"><span data-stu-id="561db-130">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="561db-131">Иными словами, если сборка кода установлена в глобальном кэше сборок, вспомогательные сборки также должны быть установлены там.</span><span class="sxs-lookup"><span data-stu-id="561db-131">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="561db-132">Если сборка кода установлена в базе кода приложения, вспомогательные сборки также должны быть установлены в папке, зависящей от языка и региональных параметров, в базе кода.</span><span class="sxs-lookup"><span data-stu-id="561db-132">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="561db-133">Если установщик Windows не используется или используется редко для установки вспомогательных сборок по требованию.</span><span class="sxs-lookup"><span data-stu-id="561db-133">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="561db-134">Когда код приложения не обрабатывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="561db-134">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="561db-135">Установка `enabled` атрибута `<relativeBindForResources>` элемента для `true` оптимизации проверки диспетчер ресурсов для вспомогательных сборок выполняется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="561db-135">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="561db-136">Он использует расположение сборки родительского кода для проверки вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="561db-136">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="561db-137">Он не запрашивает установщик Windows для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="561db-137">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="561db-138">Он не вызывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="561db-138">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561db-139">См. также</span><span class="sxs-lookup"><span data-stu-id="561db-139">See also</span></span>

- [<span data-ttu-id="561db-140">Упаковка и развертывание ресурсов</span><span class="sxs-lookup"><span data-stu-id="561db-140">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="561db-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="561db-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="561db-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="561db-142">Configuration File Schema</span></span>](../index.md)
