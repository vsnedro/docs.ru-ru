---
title: Элемент <NetFx40_LegacySecurityPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: d5192eb56bb8b640544bdc52a0bb9d8a5277efef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116251"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="2438f-102">Элемент \<NetFx40_LegacySecurityPolicy></span><span class="sxs-lookup"><span data-stu-id="2438f-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="2438f-103">Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="2438f-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**  

## <a name="syntax"></a><span data-ttu-id="2438f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2438f-104">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2438f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2438f-105">Attributes and Elements</span></span>

<span data-ttu-id="2438f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2438f-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2438f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2438f-107">Attributes</span></span>

|<span data-ttu-id="2438f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2438f-108">Attribute</span></span>|<span data-ttu-id="2438f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2438f-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2438f-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2438f-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="2438f-111">Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="2438f-111">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="2438f-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="2438f-112">enabled Attribute</span></span>

|<span data-ttu-id="2438f-113">Значение</span><span class="sxs-lookup"><span data-stu-id="2438f-113">Value</span></span>|<span data-ttu-id="2438f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2438f-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="2438f-115">Среда выполнения не использует устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="2438f-115">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="2438f-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2438f-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="2438f-117">Среда выполнения использует устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="2438f-117">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2438f-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2438f-118">Child Elements</span></span>

<span data-ttu-id="2438f-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2438f-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2438f-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2438f-120">Parent Elements</span></span>

|<span data-ttu-id="2438f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="2438f-121">Element</span></span>|<span data-ttu-id="2438f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2438f-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2438f-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2438f-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2438f-124">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2438f-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2438f-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="2438f-125">Remarks</span></span>

<span data-ttu-id="2438f-126">В .NET Framework версии 3,5 и более ранних версиях политика CAS действует всегда.</span><span class="sxs-lookup"><span data-stu-id="2438f-126">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="2438f-127">В .NET Framework 4 политика CAS должна быть включена.</span><span class="sxs-lookup"><span data-stu-id="2438f-127">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="2438f-128">Политика CAS зависит от версии.</span><span class="sxs-lookup"><span data-stu-id="2438f-128">CAS policy is version-specific.</span></span> <span data-ttu-id="2438f-129">Пользовательские политики CAS, существующие в более ранних версиях .NET Framework, должны быть указаны в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2438f-129">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="2438f-130">Применение `<NetFx40_LegacySecurityPolicy>` элемента к сборке .NET Framework 4 не влияет на прозрачный для [безопасности код](../../../misc/security-transparent-code.md); правила прозрачности по-прежнему применяются.</span><span class="sxs-lookup"><span data-stu-id="2438f-130">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2438f-131">Применение `<NetFx40_LegacySecurityPolicy>` элемента может привести к значительному снижению производительности для сборок образов в машинном кодах, созданных [генератором образов в машинном кодах (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) , которые не установлены в [глобальном кэше сборок](../../../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="2438f-131">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="2438f-132">Снижение производительности вызвано невозможностью загрузки средой выполнения сборок в качестве образов в машинном код при применении атрибута, что приводит к их загрузке как JIT-сборки.</span><span class="sxs-lookup"><span data-stu-id="2438f-132">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="2438f-133">Если указать целевую версию .NET Framework более раннюю, чем .NET Framework 4 в параметрах проекта для проекта Visual Studio, будет включена политика CAS, включая любые пользовательские политики CAS, указанные для этой версии.</span><span class="sxs-lookup"><span data-stu-id="2438f-133">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="2438f-134">Однако вы не сможете использовать новые типы и члены .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2438f-134">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="2438f-135">Можно также указать более раннюю версию .NET Framework с помощью [ \<supportedRuntime> элемента](../startup/supportedruntime-element.md) в схеме параметров запуска в [файле конфигурации приложения](../../index.md).</span><span class="sxs-lookup"><span data-stu-id="2438f-135">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2438f-136">В синтаксисе файла конфигурации учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="2438f-136">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="2438f-137">Следует использовать синтаксис, указанный в разделах синтаксис и пример.</span><span class="sxs-lookup"><span data-stu-id="2438f-137">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="2438f-138">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="2438f-138">Configuration File</span></span>

<span data-ttu-id="2438f-139">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="2438f-139">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="2438f-140">Пример</span><span class="sxs-lookup"><span data-stu-id="2438f-140">Example</span></span>

<span data-ttu-id="2438f-141">В следующем примере показано, как включить устаревшую политику CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="2438f-141">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2438f-142">См. также</span><span class="sxs-lookup"><span data-stu-id="2438f-142">See also</span></span>

- [<span data-ttu-id="2438f-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="2438f-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2438f-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="2438f-144">Configuration File Schema</span></span>](../index.md)
