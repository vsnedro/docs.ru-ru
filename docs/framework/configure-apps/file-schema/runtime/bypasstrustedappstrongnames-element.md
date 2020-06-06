---
title: Элемент <bypassTrustedAppStrongNames>
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 96361a6742d1d2f76cb237344189d3277d7c8069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739095"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="fd948-102">Элемент \<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="fd948-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="fd948-103">Указывает, следует ли обходить проверку строгих имен в сборках с полным доверием, загружаемых в полное доверие <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="fd948-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

## <a name="syntax"></a><span data-ttu-id="fd948-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd948-104">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fd948-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fd948-105">Attributes and Elements</span></span>

<span data-ttu-id="fd948-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fd948-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fd948-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fd948-107">Attributes</span></span>

|<span data-ttu-id="fd948-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fd948-108">Attribute</span></span>|<span data-ttu-id="fd948-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fd948-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="fd948-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fd948-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="fd948-111">Указывает, включена ли функция обхода, которая не позволяет проверять строгие имена для сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="fd948-111">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="fd948-112">Если эта функция включена, строгие имена не проверяются на правильность при загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="fd948-112">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="fd948-113">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="fd948-113">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="fd948-114">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="fd948-114">enabled Attribute</span></span>

|<span data-ttu-id="fd948-115">Значение</span><span class="sxs-lookup"><span data-stu-id="fd948-115">Value</span></span>|<span data-ttu-id="fd948-116">Описание</span><span class="sxs-lookup"><span data-stu-id="fd948-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="fd948-117">Подписи строгого имени в сборках с полным доверием не проверяются при загрузке сборок в режиме полного доверия <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="fd948-117">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="fd948-118">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd948-118">This is the default.</span></span>|
|`false`|<span data-ttu-id="fd948-119">Подписи строгого имени в сборках с полным доверием проверяются при загрузке сборок в режиме полного доверия <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="fd948-119">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="fd948-120">Подпись строгого имени проверяется только на правильность сигнатуры; оно не сравнивается с другим строгим именем для соответствия.</span><span class="sxs-lookup"><span data-stu-id="fd948-120">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fd948-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fd948-121">Child Elements</span></span>

<span data-ttu-id="fd948-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fd948-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fd948-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fd948-123">Parent Elements</span></span>

|<span data-ttu-id="fd948-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="fd948-124">Element</span></span>|<span data-ttu-id="fd948-125">Описание</span><span class="sxs-lookup"><span data-stu-id="fd948-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="fd948-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd948-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="fd948-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="fd948-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fd948-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd948-128">Remarks</span></span>

<span data-ttu-id="fd948-129">Функция пропуска строгих имен позволяет избежать дополнительных затрат на проверку подписи строгого имени сборок с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="fd948-129">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="fd948-130">Функция обхода применима к любой сборке, подписанной со строгим именем и имеющей следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="fd948-130">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="fd948-131">Полное доверие без <xref:System.Security.Policy.StrongName> свидетельства (например, наличие `MyComputer` свидетельства зоны).</span><span class="sxs-lookup"><span data-stu-id="fd948-131">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="fd948-132">Загрузка в домен <xref:System.AppDomain> с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="fd948-132">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="fd948-133">Загрузка из расположения со свойством <xref:System.AppDomainSetup.ApplicationBase%2A> домена <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="fd948-133">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="fd948-134">Подпись осуществлена без задержки.</span><span class="sxs-lookup"><span data-stu-id="fd948-134">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="fd948-135">Если функция обхода отключена для всех приложений на компьютере с помощью раздела реестра, этот параметр файла конфигурации не действует.</span><span class="sxs-lookup"><span data-stu-id="fd948-135">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="fd948-136">Дополнительные сведения см. в разделе [инструкции. Отключение функции обхода строгих имен](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="fd948-136">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="fd948-137">Пример</span><span class="sxs-lookup"><span data-stu-id="fd948-137">Example</span></span>

<span data-ttu-id="fd948-138">В следующем примере показано, как задать поведение, которое проверяет подпись строгого имени в сборках с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="fd948-138">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="fd948-139">См. также</span><span class="sxs-lookup"><span data-stu-id="fd948-139">See also</span></span>

- [<span data-ttu-id="fd948-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="fd948-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fd948-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fd948-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="fd948-142">Практическое руководство. Отключение функции пропуска строгих имен</span><span class="sxs-lookup"><span data-stu-id="fd948-142">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
