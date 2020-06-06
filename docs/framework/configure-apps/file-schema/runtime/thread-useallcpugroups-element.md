---
title: Элемент <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115399"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="3fb24-102">Элемент \<Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="3fb24-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="3fb24-103">Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="3fb24-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a><span data-ttu-id="3fb24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fb24-104">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3fb24-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3fb24-105">Attributes and Elements</span></span>

<span data-ttu-id="3fb24-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3fb24-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3fb24-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3fb24-107">Attributes</span></span>

|<span data-ttu-id="3fb24-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3fb24-108">Attribute</span></span>|<span data-ttu-id="3fb24-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3fb24-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="3fb24-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="3fb24-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="3fb24-111">Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="3fb24-111">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="3fb24-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="3fb24-112">enabled Attribute</span></span>

|<span data-ttu-id="3fb24-113">Значение</span><span class="sxs-lookup"><span data-stu-id="3fb24-113">Value</span></span>|<span data-ttu-id="3fb24-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3fb24-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="3fb24-115">Среда выполнения не распределяет управляемые потоки между несколькими группами ЦП.</span><span class="sxs-lookup"><span data-stu-id="3fb24-115">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="3fb24-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3fb24-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="3fb24-117">Среда выполнения распределяет управляемые потоки между несколькими группами ЦП, если компьютер имеет несколько групп ЦП и [\<GCCpuGroup>](gccpugroup-element.md) элемент включен.</span><span class="sxs-lookup"><span data-stu-id="3fb24-117">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3fb24-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3fb24-118">Child Elements</span></span>

<span data-ttu-id="3fb24-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3fb24-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3fb24-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3fb24-120">Parent Elements</span></span>

|<span data-ttu-id="3fb24-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="3fb24-121">Element</span></span>|<span data-ttu-id="3fb24-122">Описание</span><span class="sxs-lookup"><span data-stu-id="3fb24-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="3fb24-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3fb24-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="3fb24-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="3fb24-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3fb24-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="3fb24-125">Remarks</span></span>

<span data-ttu-id="3fb24-126">Если компьютер имеет несколько групп ЦП, включение этого элемента приводит к тому, что среда выполнения распределяет управляемые потоки по всем группам ЦП.</span><span class="sxs-lookup"><span data-stu-id="3fb24-126">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="3fb24-127">Чтобы использовать эту функцию, необходимо также включить [\<GCCpuGroup>](gccpugroup-element.md) элемент, который расширяет сборку мусора на все группы ЦП и учитывает все ядра при создании и балансировке куч.</span><span class="sxs-lookup"><span data-stu-id="3fb24-127">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="3fb24-128">Включение [\<GCCpuGroup>](gccpugroup-element.md) элемента требует включения [\<gcServer>](gcserver-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="3fb24-128">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="3fb24-129">Если эти элементы не включены, включение `<Thread_UseAllCpuGroups>` элемента не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="3fb24-129">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="3fb24-130">Пример</span><span class="sxs-lookup"><span data-stu-id="3fb24-130">Example</span></span>

<span data-ttu-id="3fb24-131">В следующем примере показано, как включить поддержку нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="3fb24-131">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="3fb24-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3fb24-132">See also</span></span>

- [<span data-ttu-id="3fb24-133">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="3fb24-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3fb24-134">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="3fb24-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3fb24-135">\<GCCpuGroup>Дерев</span><span class="sxs-lookup"><span data-stu-id="3fb24-135">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
