---
title: <startup> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153739"
---
# <a name="startup-element"></a><span data-ttu-id="08d00-102">Элемент \<startup></span><span class="sxs-lookup"><span data-stu-id="08d00-102">\<startup> element</span></span>

<span data-ttu-id="08d00-103">Задает сведения о запуске среды CLR.</span><span class="sxs-lookup"><span data-stu-id="08d00-103">Specifies common language runtime startup information.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<startup>**  

## <a name="syntax"></a><span data-ttu-id="08d00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08d00-104">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="08d00-105">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="08d00-105">Attributes and elements</span></span>

 <span data-ttu-id="08d00-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08d00-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="08d00-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08d00-107">Attributes</span></span>

|<span data-ttu-id="08d00-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="08d00-108">Attribute</span></span>|<span data-ttu-id="08d00-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="08d00-109">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="08d00-110">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="08d00-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="08d00-111">Указывает, следует ли включить политику активации среды выполнения .NET Framework 2,0 или использовать политику активации .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="08d00-111">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="08d00-112">атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="08d00-112">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="08d00-113">Значение</span><span class="sxs-lookup"><span data-stu-id="08d00-113">Value</span></span>|<span data-ttu-id="08d00-114">Описание</span><span class="sxs-lookup"><span data-stu-id="08d00-114">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="08d00-115">Включите политику активации среды выполнения .NET Framework 2,0 для выбранной среды выполнения, чтобы привязать устаревшие методы активации среды выполнения (например, [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) к среде выполнения, выбранной из файла конфигурации, вместо того, чтобы заключать их в CLR версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="08d00-115">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="08d00-116">Таким же, если в файле конфигурации выбрана среда CLR версии 4 или более поздней, сборки в смешанном режиме, созданные в более ранних версиях .NET Framework, загружаются с выбранной версией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="08d00-116">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="08d00-117">Установка этого значения предотвращает загрузку среды CLR версии 1,1 или CLR версии 2,0 в один и тот же процесс, фактически отключив внутрипроцессный параллельный компонент.</span><span class="sxs-lookup"><span data-stu-id="08d00-117">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="08d00-118">Используйте политику активации по умолчанию для .NET Framework 4 и более поздних версий, которая позволяет использовать устаревшие методы активации среды выполнения для загрузки среды CLR версии 1,1 или 2,0 в процесс.</span><span class="sxs-lookup"><span data-stu-id="08d00-118">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="08d00-119">Установка этого значения предотвращает загрузку сборок в смешанном режиме в .NET Framework 4 или более поздней версии, если они не были созданы с помощью .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="08d00-119">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="08d00-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08d00-120">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="08d00-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08d00-121">Child elements</span></span>

|<span data-ttu-id="08d00-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="08d00-122">Element</span></span>|<span data-ttu-id="08d00-123">Описание</span><span class="sxs-lookup"><span data-stu-id="08d00-123">Description</span></span>|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="08d00-124">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="08d00-124">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="08d00-125">В приложениях, созданных с помощью среды выполнения версии 1,1 или более поздней, должен использоваться **\<supportedRuntime>** элемент.</span><span class="sxs-lookup"><span data-stu-id="08d00-125">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="08d00-126">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="08d00-126">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="08d00-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08d00-127">Parent elements</span></span>

|<span data-ttu-id="08d00-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="08d00-128">Element</span></span>|<span data-ttu-id="08d00-129">Описание</span><span class="sxs-lookup"><span data-stu-id="08d00-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="08d00-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="08d00-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="08d00-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="08d00-131">Remarks</span></span>

 <span data-ttu-id="08d00-132">**\<supportedRuntime>** Элемент должен использоваться всеми приложениями, созданными с помощью среды выполнения версии 1,1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="08d00-132">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="08d00-133">Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать **\<requiredRuntime>** элемент.</span><span class="sxs-lookup"><span data-stu-id="08d00-133">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="08d00-134">Код запуска для приложения, размещенного в Microsoft Internet Explorer, игнорирует **\<startup>** элемент и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="08d00-134">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="08d00-135">Атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="08d00-135">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="08d00-136">Этот атрибут полезен, если ваше приложение использует пути активации прежних версий, например [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), и вы хотите, чтобы эти пути активировали версию 4 среды CLR вместо более ранней версии или если приложение создано с .NET Framework 4, но зависит от сборки в смешанном режиме, построенной с использованием более ранней версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="08d00-136">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="08d00-137">В этих сценариях задайте для атрибута значение `true` .</span><span class="sxs-lookup"><span data-stu-id="08d00-137">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="08d00-138">Установка атрибута `true` предотвращает загрузку среды CLR версии 1,1 или CLR версии 2,0 в один и тот же процесс, фактически отключив внутрипроцессный параллельный компонент (см. раздел [параллельное выполнение для COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="08d00-138">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="08d00-139">Пример</span><span class="sxs-lookup"><span data-stu-id="08d00-139">Example</span></span>

 <span data-ttu-id="08d00-140">В следующем примере показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="08d00-140">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="08d00-141">См. также</span><span class="sxs-lookup"><span data-stu-id="08d00-141">See also</span></span>

- [<span data-ttu-id="08d00-142">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="08d00-142">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="08d00-143">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="08d00-143">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="08d00-144">Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше</span><span class="sxs-lookup"><span data-stu-id="08d00-144">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="08d00-145">[Параллельное выполнение для COM- взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="08d00-145">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="08d00-146">Внутрипроцессное параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="08d00-146">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
