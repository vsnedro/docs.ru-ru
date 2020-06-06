---
title: Элемент <performanceCounters>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: f52fdb2d5b0b7911de63f96663e70735d2f2496c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697157"
---
# <a name="performancecounters-element"></a><span data-ttu-id="58dfa-102">Элемент \<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="58dfa-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="58dfa-103">Задает размер глобальной памяти, совместно используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="58dfa-103">Specifies the size of the global memory shared by performance counters.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**  

## <a name="syntax"></a><span data-ttu-id="58dfa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58dfa-104">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58dfa-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="58dfa-105">Attributes and Elements</span></span>

<span data-ttu-id="58dfa-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="58dfa-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="58dfa-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="58dfa-107">Attributes</span></span>

|<span data-ttu-id="58dfa-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="58dfa-108">Attribute</span></span>|<span data-ttu-id="58dfa-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="58dfa-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="58dfa-110">филемаппингсизе</span><span class="sxs-lookup"><span data-stu-id="58dfa-110">filemappingsize</span></span>|<span data-ttu-id="58dfa-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="58dfa-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="58dfa-112">Он указывает размер глобальной памяти в байтах, используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="58dfa-112">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="58dfa-113">Значение по умолчанию — 524288.</span><span class="sxs-lookup"><span data-stu-id="58dfa-113">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="58dfa-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="58dfa-114">Child Elements</span></span>

<span data-ttu-id="58dfa-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="58dfa-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58dfa-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="58dfa-116">Parent Elements</span></span>

|<span data-ttu-id="58dfa-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="58dfa-117">Element</span></span>|<span data-ttu-id="58dfa-118">Описание</span><span class="sxs-lookup"><span data-stu-id="58dfa-118">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="58dfa-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58dfa-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="58dfa-120">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="58dfa-120">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="58dfa-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="58dfa-121">Remarks</span></span>

<span data-ttu-id="58dfa-122">Для публикации данных производительности счетчики производительности используют размещенный в памяти файл или общую память.</span><span class="sxs-lookup"><span data-stu-id="58dfa-122">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="58dfa-123">Размер общей памяти определяет, сколько экземпляров можно использовать одновременно.</span><span class="sxs-lookup"><span data-stu-id="58dfa-123">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="58dfa-124">Существует два типа общей памяти: глобальная общая память и отдельная общая память.</span><span class="sxs-lookup"><span data-stu-id="58dfa-124">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="58dfa-125">Глобальная общая память используется всеми категориями счетчиков производительности, установленными с .NET Framework версиями 1,0 или 1,1.</span><span class="sxs-lookup"><span data-stu-id="58dfa-125">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="58dfa-126">Категории счетчиков производительности, установленные с .NET Framework версии 2,0, используют отдельную общую память, при этом каждая категория счетчиков производительности имеет собственную память.</span><span class="sxs-lookup"><span data-stu-id="58dfa-126">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="58dfa-127">Размер глобальной общей памяти можно задать только с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="58dfa-127">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="58dfa-128">Размер по умолчанию — 524 288 bДа, максимальный размер — 33 554 432 байт, а минимальный размер — 32 768 байт.</span><span class="sxs-lookup"><span data-stu-id="58dfa-128">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="58dfa-129">Так как глобальная общая память совместно используется всеми процессами и категориями, первый создатель определяет размер.</span><span class="sxs-lookup"><span data-stu-id="58dfa-129">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="58dfa-130">Если вы определяете размер в файле конфигурации приложения, этот размер используется только в том случае, если приложение является первым приложением, которое приводит к выполнению счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="58dfa-130">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="58dfa-131">Поэтому правильное расположение для указания `filemappingsize` значения — файл Machine. config.</span><span class="sxs-lookup"><span data-stu-id="58dfa-131">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="58dfa-132">Отдельные счетчики производительности не могут освободить память в глобальной общей памяти, поэтому в конечном итоге исчерпана глобальная общая память, если создано большое количество экземпляров счетчиков производительности с разными именами.</span><span class="sxs-lookup"><span data-stu-id="58dfa-132">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="58dfa-133">Для размера отдельной общей памяти необходимо сначала указать значение DWORD Филемаппингсизе в разделе реестра HKEY_LOCAL_MACHINE \Систем\куррентконтролсет\сервицес \\ *\<category name>* \перформанце, а затем значение, указанное для глобальной общей памяти в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="58dfa-133">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="58dfa-134">Если значение Филемаппингсизе не существует, то отдельный размер общей памяти устанавливается равным четвертому (1/4) глобальному параметру в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="58dfa-134">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="58dfa-135">См. также</span><span class="sxs-lookup"><span data-stu-id="58dfa-135">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
