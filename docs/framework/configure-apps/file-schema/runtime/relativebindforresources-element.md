---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153910"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="d6c26-102">Элемент \<relativeBindForResources></span><span class="sxs-lookup"><span data-stu-id="d6c26-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="d6c26-103">Оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="d6c26-103">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="d6c26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6c26-104">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6c26-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d6c26-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d6c26-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d6c26-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6c26-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d6c26-107">Attributes</span></span>  
  
|<span data-ttu-id="d6c26-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d6c26-108">Attribute</span></span>|<span data-ttu-id="d6c26-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d6c26-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d6c26-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d6c26-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="d6c26-111">Указывает, оптимизирует ли среда CLR проверку на наличие вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="d6c26-111">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d6c26-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="d6c26-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="d6c26-113">Значение</span><span class="sxs-lookup"><span data-stu-id="d6c26-113">Value</span></span>|<span data-ttu-id="d6c26-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d6c26-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d6c26-115">Среда выполнения не оптимизирует зонд для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="d6c26-115">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="d6c26-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d6c26-116">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="d6c26-117">Среда выполнения оптимизирует зонд для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="d6c26-117">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6c26-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d6c26-118">Child Elements</span></span>  
 <span data-ttu-id="d6c26-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d6c26-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6c26-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d6c26-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d6c26-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6c26-121">Element</span></span>|<span data-ttu-id="d6c26-122">Описание</span><span class="sxs-lookup"><span data-stu-id="d6c26-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d6c26-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6c26-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d6c26-124">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d6c26-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6c26-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6c26-125">Remarks</span></span>  
 <span data-ttu-id="d6c26-126">Как правило, диспетчер ресурсов зонды для ресурсов, как описано в разделе [Упаковка и развертывание ресурсов](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="d6c26-126">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="d6c26-127">Это означает, что при диспетчер ресурсов зондах для конкретной локализованной версии ресурса она может искать в глобальном кэше сборок, искать в папке, зависящей от языка и региональных параметров, в базе кода приложения, запрашивать установщик Windows для вспомогательных сборок и создавать <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="d6c26-127">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="d6c26-128">`<relativeBindForResources>`Элемент оптимизирует способ диспетчер ресурсов проверки для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="d6c26-128">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="d6c26-129">Это может повысить производительность при проверке ресурсов при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="d6c26-129">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="d6c26-130">При развертывании вспомогательной сборки в том же расположении, что и сборка кода.</span><span class="sxs-lookup"><span data-stu-id="d6c26-130">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="d6c26-131">Иными словами, если сборка кода установлена в глобальном кэше сборок, вспомогательные сборки также должны быть установлены там.</span><span class="sxs-lookup"><span data-stu-id="d6c26-131">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="d6c26-132">Если сборка кода установлена в базе кода приложения, вспомогательные сборки также должны быть установлены в папке, зависящей от языка и региональных параметров, в базе кода.</span><span class="sxs-lookup"><span data-stu-id="d6c26-132">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="d6c26-133">Если установщик Windows не используется или используется редко для установки вспомогательных сборок по требованию.</span><span class="sxs-lookup"><span data-stu-id="d6c26-133">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="d6c26-134">Когда код приложения не обрабатывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="d6c26-134">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="d6c26-135">Установка `enabled` атрибута `<relativeBindForResources>` элемента для `true` оптимизации проверки диспетчер ресурсов для вспомогательных сборок выполняется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d6c26-135">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="d6c26-136">Он использует расположение сборки родительского кода для проверки вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="d6c26-136">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="d6c26-137">Он не запрашивает установщик Windows для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="d6c26-137">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="d6c26-138">Он не вызывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="d6c26-138">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c26-139">См. также</span><span class="sxs-lookup"><span data-stu-id="d6c26-139">See also</span></span>

- [<span data-ttu-id="d6c26-140">Упаковка и развертывание ресурсов</span><span class="sxs-lookup"><span data-stu-id="d6c26-140">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="d6c26-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d6c26-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d6c26-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d6c26-142">Configuration File Schema</span></span>](../index.md)
