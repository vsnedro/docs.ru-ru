---
title: Элемент <forcePerformanceCounterUniqueSharedMemoryReads>
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 719448ba3de2aca0621fc17b9fadbdd3b8588f2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178246"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="a460e-102">Элемент \<forcePerformanceCounterUniqueSharedMemoryReads></span><span class="sxs-lookup"><span data-stu-id="a460e-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>

<span data-ttu-id="a460e-103">Указывает, использует ли файл PerfCounter.dll параметр реестра CategoryOptions в приложении .NET Framework версии 1.1, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.</span><span class="sxs-lookup"><span data-stu-id="a460e-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a><span data-ttu-id="a460e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a460e-104">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a460e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a460e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a460e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a460e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a460e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a460e-107">Attributes</span></span>  
  
|<span data-ttu-id="a460e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a460e-108">Attribute</span></span>|<span data-ttu-id="a460e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a460e-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a460e-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a460e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="a460e-111">Указывает, использует ли PerfCounter.dll параметр реестра Категорйоптионс, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.</span><span class="sxs-lookup"><span data-stu-id="a460e-111">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a460e-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="a460e-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="a460e-113">Значение</span><span class="sxs-lookup"><span data-stu-id="a460e-113">Value</span></span>|<span data-ttu-id="a460e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a460e-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a460e-115">PerfCounter.dll не использует параметр реестра Категорйоптионс, это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a460e-115">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="a460e-116">PerfCounter.dll использует параметр реестра Категорйоптионс.</span><span class="sxs-lookup"><span data-stu-id="a460e-116">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a460e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a460e-117">Child Elements</span></span>  

 <span data-ttu-id="a460e-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a460e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a460e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a460e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a460e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="a460e-120">Element</span></span>|<span data-ttu-id="a460e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a460e-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a460e-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a460e-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a460e-123">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="a460e-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a460e-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="a460e-124">Remarks</span></span>  

 <span data-ttu-id="a460e-125">В версиях .NET Framework до .NET Framework 4 версия PerfCounter.dll, которая была загружена, соответствует среде выполнения, загруженной в процессе.</span><span class="sxs-lookup"><span data-stu-id="a460e-125">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="a460e-126">Если на компьютере установлены как .NET Framework версии 1,1, так и .NET Framework 2,0, то приложение .NET Framework 1,1 загрузит .NET Framework 1,1 версии PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="a460e-126">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="a460e-127">Начиная с .NET Framework 4, загружается последняя установленная версия PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="a460e-127">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="a460e-128">Это означает, что приложение .NET Framework 1,1 будет загружать версию PerfCounter.dll .NET Framework 4, если на компьютере установлен .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a460e-128">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="a460e-129">Начиная с .NET Framework 4 при использовании счетчиков производительности PerfCounter.dll проверяет запись реестра Категорйоптионс для каждого поставщика, чтобы определить, должен ли он выполнять чтение из общей памяти конкретной категории или глобальной общей памяти.</span><span class="sxs-lookup"><span data-stu-id="a460e-129">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="a460e-130">.NET Framework 1,1 PerfCounter.dll не считывает эту запись реестра, так как она не поддерживает общую память, относящуюся к категории. Он всегда считывает данные из глобальной общей памяти.</span><span class="sxs-lookup"><span data-stu-id="a460e-130">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="a460e-131">Для обеспечения обратной совместимости .NET Framework 4 PerfCounter.dll не проверяет запись реестра Категорйоптионс при запуске в приложении .NET Framework 1,1.</span><span class="sxs-lookup"><span data-stu-id="a460e-131">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="a460e-132">Он просто использует глобальную общую память так же, как PerfCounter.dll .NET Framework 1,1.</span><span class="sxs-lookup"><span data-stu-id="a460e-132">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="a460e-133">Однако можно указать .NET Framework 4 PerfCounter.dll, чтобы проверить параметр реестра, включив `<forcePerformanceCounterUniqueSharedMemoryReads>` элемент.</span><span class="sxs-lookup"><span data-stu-id="a460e-133">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a460e-134">Включение `<forcePerformanceCounterUniqueSharedMemoryReads>` элемента не гарантирует, что будет использоваться общая память, относящаяся к категории.</span><span class="sxs-lookup"><span data-stu-id="a460e-134">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="a460e-135">Включение параметра включает `true` только PerfCounter.dll для ссылки на параметр реестра категорйоптионс.</span><span class="sxs-lookup"><span data-stu-id="a460e-135">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="a460e-136">Значение по умолчанию для Категорйоптионс — использовать общую память, относящуюся к категории; Однако можно изменить Категорйоптионс, чтобы указать, что следует использовать глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="a460e-136">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="a460e-137">Раздел реестра, содержащий параметр Категорйоптионс, — HKEY_LOCAL_MACHINE \Систем\куррентконтролсет\сервицес \\<CategoryName \> \перформанце.</span><span class="sxs-lookup"><span data-stu-id="a460e-137">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="a460e-138">По умолчанию Категорйоптионс имеет значение 3, что указывает PerfCounter.dll использовать общую память конкретной категории.</span><span class="sxs-lookup"><span data-stu-id="a460e-138">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="a460e-139">Если Категорйоптионс имеет значение 0, PerfCounter.dll использует глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="a460e-139">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="a460e-140">Данные экземпляра будут использоваться повторно только в том случае, если имя создаваемого экземпляра идентично повторно используемому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="a460e-140">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="a460e-141">Все версии будут иметь возможность записи в категорию.</span><span class="sxs-lookup"><span data-stu-id="a460e-141">All versions will be able to write to the category.</span></span> <span data-ttu-id="a460e-142">Если для Категорйоптионс задано значение 1, используется глобальная общая память, но данные экземпляра могут использоваться повторно, если длина имени категории совпадает с длиной повторно используемого категории.</span><span class="sxs-lookup"><span data-stu-id="a460e-142">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="a460e-143">Параметры 0 и 1 могут привести к утечке памяти и заполнению памяти счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="a460e-143">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a460e-144">Пример</span><span class="sxs-lookup"><span data-stu-id="a460e-144">Example</span></span>  

 <span data-ttu-id="a460e-145">В следующем примере показано, как указать, что PerfCounter.dll должен ссылаться на запись реестра Категорйоптионс, чтобы определить, должна ли она использовать общую память, относящуюся к определенной категории.</span><span class="sxs-lookup"><span data-stu-id="a460e-145">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a460e-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a460e-146">See also</span></span>

- [<span data-ttu-id="a460e-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a460e-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a460e-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a460e-148">Configuration File Schema</span></span>](../index.md)
