---
title: Гкноаффинитизе, элемент
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 16d6e5adefe2b632d7251669650058d7df7cea70
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004742"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="99729-102">Элемент \<GCNoAffinitize></span><span class="sxs-lookup"><span data-stu-id="99729-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="99729-103">Указывает, следует ли привязать потоки сервера GC с ЦП.</span><span class="sxs-lookup"><span data-stu-id="99729-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a><span data-ttu-id="99729-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99729-104">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="99729-105">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="99729-105">Attributes and elements</span></span>

<span data-ttu-id="99729-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="99729-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="99729-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="99729-107">Attributes</span></span>

|<span data-ttu-id="99729-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="99729-108">Attribute</span></span>|<span data-ttu-id="99729-109">Описание</span><span class="sxs-lookup"><span data-stu-id="99729-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="99729-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="99729-110">Required attribute.</span></span><br /><br /><span data-ttu-id="99729-111">Указывает, привязаны ли потоки или кучи серверной сборки мусора с процессорами, доступными на компьютере.</span><span class="sxs-lookup"><span data-stu-id="99729-111">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="99729-112">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="99729-112">enabled attribute</span></span>

|<span data-ttu-id="99729-113">Значение</span><span class="sxs-lookup"><span data-stu-id="99729-113">Value</span></span>|<span data-ttu-id="99729-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="99729-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="99729-115">Потоки GC сервера аффинитизес с ЦП.</span><span class="sxs-lookup"><span data-stu-id="99729-115">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="99729-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99729-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="99729-117">Не привязать потоки GC сервера с процессорами.</span><span class="sxs-lookup"><span data-stu-id="99729-117">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="99729-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="99729-118">Child elements</span></span>

<span data-ttu-id="99729-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="99729-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="99729-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="99729-120">Parent elements</span></span>

|<span data-ttu-id="99729-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="99729-121">Element</span></span>|<span data-ttu-id="99729-122">Описание</span><span class="sxs-lookup"><span data-stu-id="99729-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="99729-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99729-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="99729-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="99729-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="99729-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="99729-125">Remarks</span></span>

<span data-ttu-id="99729-126">По умолчанию потоки GC сервера жестко привязаны с соответствующими процессорами.</span><span class="sxs-lookup"><span data-stu-id="99729-126">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="99729-127">Каждый из доступных процессоров системы имеет собственную кучу сборщика мусора и поток.</span><span class="sxs-lookup"><span data-stu-id="99729-127">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="99729-128">Обычно это предпочтительный параметр, так как он оптимизирует использование кэша.</span><span class="sxs-lookup"><span data-stu-id="99729-128">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="99729-129">Начиная с .NET Framework 4.6.2, установив для атрибута элемента **гкноаффинитизе** значение `enabled` `true` , можно указать, что потоки и процессоры GC сервера не должны быть тесно связаны.</span><span class="sxs-lookup"><span data-stu-id="99729-129">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `true`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="99729-130">Можно указать только элемент конфигурации **гкноаффинитизе** , чтобы не ПРИВЯЗАТЬ потоки GC сервера с процессорами.</span><span class="sxs-lookup"><span data-stu-id="99729-130">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="99729-131">Кроме того, его можно использовать вместе с элементом [гчеапкаунт](gcheapcount-element.md) для управления числом куч и потоков GC, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="99729-131">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="99729-132">Если `enabled` атрибут элемента **гкноаффинитизе** имеет `false` (значение по умолчанию), можно также использовать элемент [гчеапкаунт](gcheapcount-element.md) , чтобы указать количество потоков и куч GC вместе с элементом [гчеапаффинитиземаск](gcheapaffinitizemask-element.md) , чтобы указать процессоры, к которым будут привязаныся потоки и кучи GC.</span><span class="sxs-lookup"><span data-stu-id="99729-132">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="99729-133">Пример</span><span class="sxs-lookup"><span data-stu-id="99729-133">Example</span></span>

<span data-ttu-id="99729-134">В следующем примере не привязать потоки GC сервера.</span><span class="sxs-lookup"><span data-stu-id="99729-134">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="99729-135">В следующем примере не привязать потоки сервера GC и ограничивает число куч/потоков GC до 10:</span><span class="sxs-lookup"><span data-stu-id="99729-135">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="99729-136">См. также статью</span><span class="sxs-lookup"><span data-stu-id="99729-136">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="99729-137">Гчеапаффинитиземаск, элемент</span><span class="sxs-lookup"><span data-stu-id="99729-137">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="99729-138">Гчеапкаунт, элемент</span><span class="sxs-lookup"><span data-stu-id="99729-138">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="99729-139">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="99729-139">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="99729-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="99729-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="99729-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="99729-141">Configuration File Schema</span></span>](../index.md)
