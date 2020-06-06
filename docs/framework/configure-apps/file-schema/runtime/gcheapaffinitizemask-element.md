---
title: Гчеапаффинитиземаск, элемент
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73978423"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="ec0ff-102">Элемент \<GCHeapAffinitizeMask></span><span class="sxs-lookup"><span data-stu-id="ec0ff-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="ec0ff-103">Определяет сходство между кучами сборщика мусора и отдельными процессорами.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-103">Defines the affinity between GC heaps and individual processors.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask>

## <a name="syntax"></a><span data-ttu-id="ec0ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec0ff-104">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec0ff-105">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec0ff-105">Attributes and elements</span></span>

<span data-ttu-id="ec0ff-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec0ff-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec0ff-107">Attributes</span></span>

|<span data-ttu-id="ec0ff-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ec0ff-108">Attribute</span></span>|<span data-ttu-id="ec0ff-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ec0ff-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="ec0ff-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-110">Required attribute.</span></span><br /><br /><span data-ttu-id="ec0ff-111">Указывает сходство между кучами сборщика мусора и отдельными процессорами.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-111">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="ec0ff-112">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="ec0ff-112">enabled attribute</span></span>

|<span data-ttu-id="ec0ff-113">Значение</span><span class="sxs-lookup"><span data-stu-id="ec0ff-113">Value</span></span>|<span data-ttu-id="ec0ff-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ec0ff-114">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="ec0ff-115">Десятичное значение, которое образует битовую маску для определения сходства между кучами сервера GC и отдельными процессорами.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-115">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="ec0ff-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec0ff-116">Child elements</span></span>

<span data-ttu-id="ec0ff-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ec0ff-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec0ff-118">Parent elements</span></span>

|<span data-ttu-id="ec0ff-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec0ff-119">Element</span></span>|<span data-ttu-id="ec0ff-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ec0ff-120">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ec0ff-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="ec0ff-122">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-122">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ec0ff-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec0ff-123">Remarks</span></span>

<span data-ttu-id="ec0ff-124">По умолчанию потоки GC сервера жестко привязаны с соответствующими ПРОЦЕССОРами, чтобы существовала одна Куча сборщика мусора, один поток GC сервера и один поток GC для каждого процессора.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-124">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="ec0ff-125">Начиная с .NET Framework 4.6.2, можно использовать элемент **гчеапаффинитиземаск** для управления соответствием между кучами и процессорами сервера GC, если число куч ограничено элементом **гчеапкаунт** .</span><span class="sxs-lookup"><span data-stu-id="ec0ff-125">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="ec0ff-126">**Гчеапаффинитиземаск** обычно используется вместе с двумя другими флагами:</span><span class="sxs-lookup"><span data-stu-id="ec0ff-126">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="ec0ff-127">[Гкноаффинитизе](gcnoaffinitize-element.md), который управляет тем, привязаны ли потоки или КУЧИ сервера GC с ЦП.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-127">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="ec0ff-128">`enabled`Для использования параметра гчеапаффинитиземаск атрибут элемента [гкноаффинитизе](gcnoaffinitize-element.md) должен быть `false` (его значение по умолчанию **GCHeapAffinitizeMask** ).</span><span class="sxs-lookup"><span data-stu-id="ec0ff-128">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="ec0ff-129">[Гчеапкаунт](gcheapcount-element.md), ограничивающее количество куч, используемых процессом для сервера GC.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-129">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="ec0ff-130">По умолчанию для каждого процессора существует одна куча.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-130">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="ec0ff-131">**nnnn** — это битовая маска, выраженная в виде десятичного значения.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-131">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="ec0ff-132">Бит 0 байт 0 представляет процессор 0, бит 1 байт 0 представляет процессор 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-132">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="ec0ff-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="ec0ff-133">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="ec0ff-134">Значение 1023 — 0x3FF или 0011 1111 1111b.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-134">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="ec0ff-135">Процесс использует 10 процессоров, от процессора 0 до процессора 9.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-135">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="ec0ff-136">Пример</span><span class="sxs-lookup"><span data-stu-id="ec0ff-136">Example</span></span>

<span data-ttu-id="ec0ff-137">В следующем примере показано, что приложение использует серверную сборку мусора с 10 кучами и потоками.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-137">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="ec0ff-138">Так как вы не хотите, чтобы эти кучи перекрывались с кучами из других приложений, работающих в системе, используйте **гчеапаффинитиземаск** , чтобы указать, что процесс должен использовать процессоры от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="ec0ff-138">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ec0ff-139">См. также</span><span class="sxs-lookup"><span data-stu-id="ec0ff-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ec0ff-140">Гкноаффинитизе, элемент</span><span class="sxs-lookup"><span data-stu-id="ec0ff-140">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="ec0ff-141">Гчеапкаунт, элемент</span><span class="sxs-lookup"><span data-stu-id="ec0ff-141">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="ec0ff-142">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="ec0ff-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="ec0ff-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ec0ff-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ec0ff-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ec0ff-144">Configuration File Schema</span></span>](../index.md)
