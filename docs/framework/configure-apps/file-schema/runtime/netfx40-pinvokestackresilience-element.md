---
title: Элемент <NetFx40_PInvokeStackResilience>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116162"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="7f31a-102">Элемент \<NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="7f31a-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="7f31a-103">Указывает, исправляет ли автоматически среда выполнения неправильные объявления вызова неуправляемого кода во время выполнения за счет скорости перехода между управляемыми и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="7f31a-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a><span data-ttu-id="7f31a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f31a-104">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f31a-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7f31a-105">Attributes and Elements</span></span>

<span data-ttu-id="7f31a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7f31a-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f31a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f31a-107">Attributes</span></span>

|<span data-ttu-id="7f31a-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7f31a-108">Attribute</span></span>|<span data-ttu-id="7f31a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7f31a-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="7f31a-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="7f31a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="7f31a-111">Указывает, обнаруживает ли среда выполнения неверные объявления вызова неуправляемого кода и автоматически исправляет стек во время выполнения на 32-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="7f31a-111">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="7f31a-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="7f31a-112">enabled Attribute</span></span>

|<span data-ttu-id="7f31a-113">Значение</span><span class="sxs-lookup"><span data-stu-id="7f31a-113">Value</span></span>|<span data-ttu-id="7f31a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7f31a-114">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="7f31a-115">Среда выполнения использует более быструю архитектуру маршалинга взаимодействия, представленную в .NET Framework 4, которая не обнаруживает и не устраняет неверные объявления вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7f31a-115">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="7f31a-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7f31a-116">This is the default.</span></span>|
|`1`|<span data-ttu-id="7f31a-117">Среда выполнения использует медленные переходы, которые обнаруживают и исправляют неверные объявления вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7f31a-117">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7f31a-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7f31a-118">Child Elements</span></span>

<span data-ttu-id="7f31a-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7f31a-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7f31a-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7f31a-120">Parent Elements</span></span>

|<span data-ttu-id="7f31a-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f31a-121">Element</span></span>|<span data-ttu-id="7f31a-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7f31a-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="7f31a-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f31a-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="7f31a-124">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7f31a-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="7f31a-125">Remarks</span></span>

<span data-ttu-id="7f31a-126">Этот элемент позволяет ускорить маршалинг взаимодействия для устойчивости во время выполнения по неправильным объявлениям вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7f31a-126">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="7f31a-127">Начиная с .NET Framework 4, оптимизированная архитектура маршалинга взаимодействия обеспечивает значительное повышение производительности при переходе от управляемого кода к неуправляемому.</span><span class="sxs-lookup"><span data-stu-id="7f31a-127">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="7f31a-128">В более ранних версиях .NET Framework слой упаковки обнаружил неверные объявления вызова неуправляемого кода на 32-разрядных платформах и автоматически устранил стек.</span><span class="sxs-lookup"><span data-stu-id="7f31a-128">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="7f31a-129">Новая архитектура маршалирования устраняет этот шаг.</span><span class="sxs-lookup"><span data-stu-id="7f31a-129">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="7f31a-130">В результате переходы выполняются очень быстро, но неправильное объявление вызова неуправляемого кода может привести к сбою программы.</span><span class="sxs-lookup"><span data-stu-id="7f31a-130">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="7f31a-131">Чтобы упростить обнаружение неверных объявлений во время разработки, улучшен процесс отладки в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7f31a-131">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="7f31a-132">Помощник по отладке управляемого кода [пинвокестаккимбаланце](../../../debug-trace-profile/pinvokestackimbalance-mda.md) (MDA) уведомляет вас о неправильном объявлении вызова платформы, когда приложение выполняется с присоединенным отладчиком.</span><span class="sxs-lookup"><span data-stu-id="7f31a-132">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="7f31a-133">Для решения сценариев, в которых приложение использует компоненты, которые нельзя перекомпилировать, с неправильными объявлениями вызова неуправляемого кода, можно использовать `NetFx40_PInvokeStackResilience` элемент.</span><span class="sxs-lookup"><span data-stu-id="7f31a-133">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="7f31a-134">Добавление этого элемента в файл конфигурации приложения с `enabled="1"` режимом совместимости с поведением более ранних версий .NET Framework за счет более медленных переходов.</span><span class="sxs-lookup"><span data-stu-id="7f31a-134">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="7f31a-135">Сборки, скомпилированные для более ранних версий .NET Framework, автоматически включаются в этот режим совместимости и не нуждаются в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="7f31a-135">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="7f31a-136">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="7f31a-136">Configuration File</span></span>

<span data-ttu-id="7f31a-137">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-137">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="7f31a-138">Пример</span><span class="sxs-lookup"><span data-stu-id="7f31a-138">Example</span></span>

<span data-ttu-id="7f31a-139">В следующем примере показано, как выбрать повышенную устойчивость к неправильным объявлениям вызова неуправляемого кода для приложения за счет более медленных переходов между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="7f31a-139">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7f31a-140">См. также</span><span class="sxs-lookup"><span data-stu-id="7f31a-140">See also</span></span>

- [<span data-ttu-id="7f31a-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="7f31a-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7f31a-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="7f31a-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7f31a-143">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="7f31a-143">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
