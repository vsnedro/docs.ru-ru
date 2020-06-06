---
title: <requiredRuntime> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697487"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="6f36b-102">Элемент \<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="6f36b-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="6f36b-103">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6f36b-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="6f36b-104">Этот элемент является устаревшим и больше не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="6f36b-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="6f36b-105">[`supportedRuntime`](supportedruntime-element.md)Вместо этого следует использовать элемент.</span><span class="sxs-lookup"><span data-stu-id="6f36b-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a><span data-ttu-id="6f36b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f36b-106">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6f36b-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="6f36b-107">Attributes and elements</span></span>

<span data-ttu-id="6f36b-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6f36b-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6f36b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6f36b-109">Attributes</span></span>

|<span data-ttu-id="6f36b-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6f36b-110">Attribute</span></span>|<span data-ttu-id="6f36b-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="6f36b-111">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="6f36b-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6f36b-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6f36b-113">Строковое значение, указывающее версию .NET Framework, которую поддерживает это приложение.</span><span class="sxs-lookup"><span data-stu-id="6f36b-113">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="6f36b-114">Строковое значение должно соответствовать имени каталога, обнаруженному в корне установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f36b-114">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="6f36b-115">Содержимое строкового значения не анализируется.</span><span class="sxs-lookup"><span data-stu-id="6f36b-115">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="6f36b-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6f36b-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6f36b-117">Указывает, будет ли код запуска среды выполнения выполнять поиск в реестре для определения версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f36b-117">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="6f36b-118">атрибут безопасный режим</span><span class="sxs-lookup"><span data-stu-id="6f36b-118">safemode attribute</span></span>

|<span data-ttu-id="6f36b-119">Значение</span><span class="sxs-lookup"><span data-stu-id="6f36b-119">Value</span></span>|<span data-ttu-id="6f36b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6f36b-120">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="6f36b-121">Код запуска среды выполнения выполняет поиск в реестре.</span><span class="sxs-lookup"><span data-stu-id="6f36b-121">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="6f36b-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6f36b-122">This is the default value.</span></span>|
|`true`|<span data-ttu-id="6f36b-123">Код запуска среды выполнения не выполняет поиск в реестре.</span><span class="sxs-lookup"><span data-stu-id="6f36b-123">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6f36b-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6f36b-124">Child elements</span></span>

<span data-ttu-id="6f36b-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6f36b-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6f36b-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6f36b-126">Parent elements</span></span>

|<span data-ttu-id="6f36b-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="6f36b-127">Element</span></span>|<span data-ttu-id="6f36b-128">Описание</span><span class="sxs-lookup"><span data-stu-id="6f36b-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="6f36b-129">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f36b-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="6f36b-130">Содержит `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="6f36b-130">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6f36b-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f36b-131">Remarks</span></span>
 <span data-ttu-id="6f36b-132">Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="6f36b-132">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="6f36b-133">Приложения, созданные с помощью версии 1,1 или более поздней версии среды выполнения, должны использовать `<supportedRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="6f36b-133">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="6f36b-134">При использовании функции [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для указания файла конфигурации необходимо использовать `<requiredRuntime>` элемент для всех версий среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f36b-134">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="6f36b-135">`<supportedRuntime>`При использовании [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)элемент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="6f36b-135">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="6f36b-136">`version`Строка атрибута должна соответствовать имени папки установки для указанной версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f36b-136">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="6f36b-137">Эта строка не интерпретируется.</span><span class="sxs-lookup"><span data-stu-id="6f36b-137">This string is not interpreted.</span></span> <span data-ttu-id="6f36b-138">Если код запуска среды выполнения не находит совпадающую папку, среда выполнения не загружается; код запуска отображает сообщение об ошибке и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="6f36b-138">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="6f36b-139">Код запуска для приложения, размещенного в Microsoft Internet Explorer, игнорирует `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="6f36b-139">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="6f36b-140">Пример</span><span class="sxs-lookup"><span data-stu-id="6f36b-140">Example</span></span>

<span data-ttu-id="6f36b-141">В следующем примере показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f36b-141">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6f36b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="6f36b-142">See also</span></span>

- [<span data-ttu-id="6f36b-143">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="6f36b-143">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6f36b-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="6f36b-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6f36b-145">Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше</span><span class="sxs-lookup"><span data-stu-id="6f36b-145">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
