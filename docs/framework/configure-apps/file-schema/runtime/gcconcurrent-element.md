---
title: gcConcurrent, элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 249518ae7477d284d50f9010757db83b7752c657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102922"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="51c0f-102">Элемент \<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="51c0f-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="51c0f-103">Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="51c0f-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent>

## <a name="syntax"></a><span data-ttu-id="51c0f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51c0f-104">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="51c0f-105">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="51c0f-105">Attributes and elements</span></span>

<span data-ttu-id="51c0f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="51c0f-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="51c0f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51c0f-107">Attributes</span></span>

|<span data-ttu-id="51c0f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="51c0f-108">Attribute</span></span>|<span data-ttu-id="51c0f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="51c0f-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="51c0f-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="51c0f-110">Required attribute.</span></span><br /><br /><span data-ttu-id="51c0f-111">Указывает, выполняет ли среда выполнения сборку мусора параллельно.</span><span class="sxs-lookup"><span data-stu-id="51c0f-111">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="51c0f-112">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="51c0f-112">enabled attribute</span></span>

|<span data-ttu-id="51c0f-113">Значение</span><span class="sxs-lookup"><span data-stu-id="51c0f-113">Value</span></span>|<span data-ttu-id="51c0f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="51c0f-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="51c0f-115">Не выполняется параллельное выполнение сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="51c0f-115">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="51c0f-116">Сборка мусора выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="51c0f-116">Runs garbage collection concurrently.</span></span> <span data-ttu-id="51c0f-117">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51c0f-117">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="51c0f-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51c0f-118">Child elements</span></span>

<span data-ttu-id="51c0f-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="51c0f-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="51c0f-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="51c0f-120">Parent elements</span></span>

|<span data-ttu-id="51c0f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="51c0f-121">Element</span></span>|<span data-ttu-id="51c0f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="51c0f-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="51c0f-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51c0f-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="51c0f-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="51c0f-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="51c0f-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="51c0f-125">Remarks</span></span>

<span data-ttu-id="51c0f-126">До .NET Framework 4 сборка мусора рабочей станции поддерживала параллельную сборку мусора, которая выполняла сборку мусора в фоновом режиме в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="51c0f-126">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="51c0f-127">В .NET Framework 4 параллельная сборка мусора была заменена фоновым GC, который также выполняет сборку мусора в фоновом режиме в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="51c0f-127">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="51c0f-128">Начиная с .NET Framework 4,5, фоновая коллекция стала доступна в процессе сборки мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="51c0f-128">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="51c0f-129">Элемент **gcConcurrent** определяет, выполняет ли среда выполнения параллельную или фоновую сборку мусора, если она доступна, или же она выполняет сборку мусора на переднем плане.</span><span class="sxs-lookup"><span data-stu-id="51c0f-129">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="51c0f-130">Отключение фоновой сборки мусора</span><span class="sxs-lookup"><span data-stu-id="51c0f-130">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="51c0f-131">Начиная с .NET Framework 4, параллельная сборка мусора заменяется фоновой сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="51c0f-131">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="51c0f-132">*Одновременные* и *фоновые* термины в документации по .NET Framework используются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="51c0f-132">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="51c0f-133">Чтобы отключить фоновую сборку мусора, используйте элемент **gcConcurrent** , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="51c0f-133">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="51c0f-134">По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам.</span><span class="sxs-lookup"><span data-stu-id="51c0f-134">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="51c0f-135">Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="51c0f-135">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="51c0f-136">Если задать `enabled` для атрибута элемента **gcConcurrent** значение `false` , среда выполнения использует непараллельную сборку мусора, оптимизированную для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="51c0f-136">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="51c0f-137">Следующий файл конфигурации отключает фоновую сборку мусора:</span><span class="sxs-lookup"><span data-stu-id="51c0f-137">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="51c0f-138">Если в файле конфигурации компьютера есть параметр **гкконкуррентсеттинг** , он определяет значение по умолчанию для всех .NET Framework приложений.</span><span class="sxs-lookup"><span data-stu-id="51c0f-138">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="51c0f-139">Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="51c0f-139">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="51c0f-140">Дополнительные сведения о параллельной и фоновой сборке мусора см. в разделе [Фоновая сборка мусора](../../../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="51c0f-140">For more information on concurrent and background garbage collection, see [Background garbage collection](../../../../standard/garbage-collection/background-gc.md).</span></span>

## <a name="example"></a><span data-ttu-id="51c0f-141">Пример</span><span class="sxs-lookup"><span data-stu-id="51c0f-141">Example</span></span>

<span data-ttu-id="51c0f-142">В следующем примере включается фоновая сборка мусора:</span><span class="sxs-lookup"><span data-stu-id="51c0f-142">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="51c0f-143">См. также</span><span class="sxs-lookup"><span data-stu-id="51c0f-143">See also</span></span>

- [<span data-ttu-id="51c0f-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="51c0f-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="51c0f-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="51c0f-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="51c0f-146">Основные принципы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="51c0f-146">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
