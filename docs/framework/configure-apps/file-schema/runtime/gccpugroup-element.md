---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102896"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="52da0-102">\<GCCpuGroup> Элемент</span><span class="sxs-lookup"><span data-stu-id="52da0-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="52da0-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="52da0-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="52da0-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52da0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52da0-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="52da0-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="52da0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span><span class="sxs-lookup"><span data-stu-id="52da0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="52da0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52da0-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="52da0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52da0-108">Attributes and Elements</span></span>

<span data-ttu-id="52da0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="52da0-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="52da0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52da0-110">Attributes</span></span>

|<span data-ttu-id="52da0-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="52da0-111">Attribute</span></span>|<span data-ttu-id="52da0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="52da0-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="52da0-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="52da0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="52da0-114">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="52da0-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="52da0-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="52da0-115">enabled Attribute</span></span>

|<span data-ttu-id="52da0-116">Значение</span><span class="sxs-lookup"><span data-stu-id="52da0-116">Value</span></span>|<span data-ttu-id="52da0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="52da0-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="52da0-118">Сбор мусора не поддерживает несколько групп процессоров.</span><span class="sxs-lookup"><span data-stu-id="52da0-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="52da0-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="52da0-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="52da0-120">Сбор мусора поддерживает несколько групп процессоров, если включен сбор мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="52da0-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="52da0-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52da0-121">Child Elements</span></span>

<span data-ttu-id="52da0-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="52da0-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="52da0-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52da0-123">Parent Elements</span></span>

|<span data-ttu-id="52da0-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="52da0-124">Element</span></span>|<span data-ttu-id="52da0-125">Описание</span><span class="sxs-lookup"><span data-stu-id="52da0-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="52da0-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52da0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="52da0-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="52da0-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="52da0-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="52da0-128">Remarks</span></span>

<span data-ttu-id="52da0-129">Когда компьютер имеет несколько групп процессоров и сбор мусора сервера включен (см. [ \<элемент gcServer>),](gcserver-element.md) что позволяет этот элемент расширяет сбор мусора во всех группах процессоров и принимает все ядра во внимание при создании и балансировке кучи.</span><span class="sxs-lookup"><span data-stu-id="52da0-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="52da0-130">Этот элемент применяется только к потокам сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="52da0-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="52da0-131">Чтобы включить время выполнения для распределения потоков пользователей по всем группам процессора, необходимо также включить [ \<элемент Thread_UseAllCpuGroups>.](thread-useallcpugroups-element.md)</span><span class="sxs-lookup"><span data-stu-id="52da0-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="52da0-132">Пример</span><span class="sxs-lookup"><span data-stu-id="52da0-132">Example</span></span>

<span data-ttu-id="52da0-133">В следующем примере показано, как включить сбор мусора для нескольких групп процессоров.</span><span class="sxs-lookup"><span data-stu-id="52da0-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="52da0-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="52da0-134">See also</span></span>

- [<span data-ttu-id="52da0-135">Схема настройки выполнения</span><span class="sxs-lookup"><span data-stu-id="52da0-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="52da0-136">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="52da0-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="52da0-137">Отключить параллельный сбор мусора</span><span class="sxs-lookup"><span data-stu-id="52da0-137">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="52da0-138">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="52da0-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
