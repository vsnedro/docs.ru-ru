---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102896"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="9d1a3-102">Элемент \<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="9d1a3-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="9d1a3-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a><span data-ttu-id="9d1a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d1a3-104">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d1a3-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9d1a3-105">Attributes and Elements</span></span>

<span data-ttu-id="9d1a3-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d1a3-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d1a3-107">Attributes</span></span>

|<span data-ttu-id="9d1a3-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9d1a3-108">Attribute</span></span>|<span data-ttu-id="9d1a3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9d1a3-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="9d1a3-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="9d1a3-111">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-111">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="9d1a3-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="9d1a3-112">enabled Attribute</span></span>

|<span data-ttu-id="9d1a3-113">Значение</span><span class="sxs-lookup"><span data-stu-id="9d1a3-113">Value</span></span>|<span data-ttu-id="9d1a3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9d1a3-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="9d1a3-115">Сборка мусора не поддерживает несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-115">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="9d1a3-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="9d1a3-117">Сборка мусора поддерживает несколько групп ЦП, если включена сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-117">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9d1a3-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9d1a3-118">Child Elements</span></span>

<span data-ttu-id="9d1a3-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d1a3-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9d1a3-120">Parent Elements</span></span>

|<span data-ttu-id="9d1a3-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d1a3-121">Element</span></span>|<span data-ttu-id="9d1a3-122">Описание</span><span class="sxs-lookup"><span data-stu-id="9d1a3-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="9d1a3-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="9d1a3-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9d1a3-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d1a3-125">Remarks</span></span>

<span data-ttu-id="9d1a3-126">Если на компьютере установлено несколько групп ЦП и включена сборка мусора сервера (см. [\<gcServer>](gcserver-element.md) элемент), включение этого элемента расширяет сбор мусора во всех группах ЦП и учитывает все ядра при создании и балансировке куч.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-126">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="9d1a3-127">Этот элемент применяется только к потокам сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-127">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="9d1a3-128">Чтобы среда выполнения распространяла пользовательские потоки во всех группах ЦП, необходимо также включить [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-128">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="9d1a3-129">Пример</span><span class="sxs-lookup"><span data-stu-id="9d1a3-129">Example</span></span>

<span data-ttu-id="9d1a3-130">В следующем примере показано, как включить сбор мусора для нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="9d1a3-130">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="9d1a3-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9d1a3-131">See also</span></span>

- [<span data-ttu-id="9d1a3-132">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="9d1a3-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9d1a3-133">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="9d1a3-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9d1a3-134">Отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="9d1a3-134">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="9d1a3-135">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="9d1a3-135">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
