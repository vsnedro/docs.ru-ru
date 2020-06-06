---
title: Гклохсрешолд, элемент
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74451326"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="fe22b-102">Гклохсрешолд, элемент</span><span class="sxs-lookup"><span data-stu-id="fe22b-102">GCLOHThreshold element</span></span>

<span data-ttu-id="fe22b-103">Указывает пороговый размер (в байтах), который заставляет сборщик мусора разместить объекты в куче больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="fe22b-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a><span data-ttu-id="fe22b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe22b-104">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="fe22b-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fe22b-105">Attributes</span></span>

|<span data-ttu-id="fe22b-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fe22b-106">Attribute</span></span>|<span data-ttu-id="fe22b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fe22b-107">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="fe22b-108">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fe22b-108">Required attribute.</span></span><br /><br /><span data-ttu-id="fe22b-109">Указывает пороговый размер, который приводит к тому, что объекты попадают в кучу больших объектов.</span><span class="sxs-lookup"><span data-stu-id="fe22b-109">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="fe22b-110">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="fe22b-110">enabled attribute</span></span>

|<span data-ttu-id="fe22b-111">Значение</span><span class="sxs-lookup"><span data-stu-id="fe22b-111">Value</span></span>|<span data-ttu-id="fe22b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fe22b-112">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="fe22b-113">Пороговый размер (в байтах), который приводит к тому, что объекты попадают в кучу больших объектов.</span><span class="sxs-lookup"><span data-stu-id="fe22b-113">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="fe22b-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fe22b-114">Child elements</span></span>

<span data-ttu-id="fe22b-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fe22b-115">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="fe22b-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fe22b-116">Parent elements</span></span>

|<span data-ttu-id="fe22b-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="fe22b-117">Element</span></span>|<span data-ttu-id="fe22b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="fe22b-118">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="fe22b-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fe22b-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="fe22b-120">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="fe22b-120">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fe22b-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe22b-121">Remarks</span></span>

<span data-ttu-id="fe22b-122">Этот параметр появился в .NET Framework 4,8.</span><span class="sxs-lookup"><span data-stu-id="fe22b-122">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe22b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fe22b-123">See also</span></span>

- [<span data-ttu-id="fe22b-124">Схема параметров времени выполнения</span><span class="sxs-lookup"><span data-stu-id="fe22b-124">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="fe22b-125">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fe22b-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="fe22b-126">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="fe22b-126">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="fe22b-127">Параметры конфигурации среды выполнения NET Core для GC</span><span class="sxs-lookup"><span data-stu-id="fe22b-127">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
