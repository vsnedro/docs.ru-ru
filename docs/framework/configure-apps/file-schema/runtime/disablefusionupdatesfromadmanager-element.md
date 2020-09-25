---
title: Элемент <disableFusionUpdatesFromADManager>
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: c3971379b358ae16fc463df2b8d6288cf8881391
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205039"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="3da06-102">Элемент \<disableFusionUpdatesFromADManager></span><span class="sxs-lookup"><span data-stu-id="3da06-102">\<disableFusionUpdatesFromADManager> Element</span></span>

<span data-ttu-id="3da06-103">Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3da06-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a><span data-ttu-id="3da06-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3da06-104">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3da06-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3da06-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3da06-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3da06-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3da06-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3da06-107">Attributes</span></span>  
  
|<span data-ttu-id="3da06-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3da06-108">Attribute</span></span>|<span data-ttu-id="3da06-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3da06-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3da06-110">Включено</span><span class="sxs-lookup"><span data-stu-id="3da06-110">enabled</span></span>|<span data-ttu-id="3da06-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="3da06-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="3da06-112">Указывает, отключена ли возможность по умолчанию переопределять параметры Fusion.</span><span class="sxs-lookup"><span data-stu-id="3da06-112">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3da06-113">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="3da06-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="3da06-114">Значение</span><span class="sxs-lookup"><span data-stu-id="3da06-114">Value</span></span>|<span data-ttu-id="3da06-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3da06-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3da06-116">0</span><span class="sxs-lookup"><span data-stu-id="3da06-116">0</span></span>|<span data-ttu-id="3da06-117">Не отключайте возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="3da06-117">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="3da06-118">Это поведение по умолчанию, начиная с .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3da06-118">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="3da06-119">1</span><span class="sxs-lookup"><span data-stu-id="3da06-119">1</span></span>|<span data-ttu-id="3da06-120">Отключить возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="3da06-120">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="3da06-121">Это позволяет вернуться к поведению более ранних версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3da06-121">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3da06-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3da06-122">Child Elements</span></span>  

 <span data-ttu-id="3da06-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3da06-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3da06-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3da06-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3da06-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="3da06-125">Element</span></span>|<span data-ttu-id="3da06-126">Описание</span><span class="sxs-lookup"><span data-stu-id="3da06-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3da06-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3da06-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3da06-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="3da06-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3da06-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="3da06-129">Remarks</span></span>  

 <span data-ttu-id="3da06-130">Начиная с .NET Framework 4, поведение по умолчанию заключается в том, чтобы разрешить <xref:System.AppDomainManager> объекту переопределять параметры конфигурации с помощью <xref:System.AppDomainSetup.ConfigurationFile%2A> свойства или <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метода <xref:System.AppDomainSetup> объекта, который передается в вашу реализацию <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метода, в подкласс <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="3da06-130">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="3da06-131">Для домена приложения по умолчанию измененные параметры переопределяют параметры, заданные в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="3da06-131">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="3da06-132">Для других доменов приложений они переопределяют параметры конфигурации, переданные в <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> метод или.</span><span class="sxs-lookup"><span data-stu-id="3da06-132">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3da06-133">Можно либо передать новые сведения о конфигурации, либо передать значение null ( `Nothing` в Visual Basic), чтобы исключить переданные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3da06-133">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="3da06-134">Не следует передавать сведения о конфигурации как в <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство, так и в <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="3da06-134">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="3da06-135">Если данные о конфигурации передаются в оба значения, то данные, передаваемые в <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство, игнорируются, так как <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод переопределяет сведения о конфигурации из файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="3da06-135">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="3da06-136">При использовании <xref:System.AppDomainSetup.ConfigurationFile%2A> свойства можно передать значение null ( `Nothing` в Visual Basic) <xref:System.AppDomainSetup.SetConfigurationBytes%2A> методу, чтобы исключить все байты конфигурации, указанные в вызове <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> метода или.</span><span class="sxs-lookup"><span data-stu-id="3da06-136">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3da06-137">Помимо сведений о конфигурации, можно изменить следующие параметры <xref:System.AppDomainSetup> объекта, который передается в реализацию <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метода:,,,,, <xref:System.AppDomainSetup.ApplicationBase%2A> <xref:System.AppDomainSetup.ApplicationName%2A> <xref:System.AppDomainSetup.CachePath%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowCodeDownload%2A> , <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A> , <xref:System.AppDomainSetup.DynamicBase%2A> ,,,, <xref:System.AppDomainSetup.LoaderOptimization%2A> <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> и <xref:System.AppDomainSetup.ShadowCopyFiles%2A> .</span><span class="sxs-lookup"><span data-stu-id="3da06-137">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="3da06-138">В качестве альтернативы использованию `<disableFusionUpdatesFromADManager>` элемента можно отключить поведение по умолчанию, создав параметр реестра или задав переменную среды.</span><span class="sxs-lookup"><span data-stu-id="3da06-138">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="3da06-139">В реестре создайте значение DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` в разделе `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework` и установите значение 1.</span><span class="sxs-lookup"><span data-stu-id="3da06-139">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="3da06-140">В командной строке задайте для переменной среды значение `COMPLUS_disableFusionUpdatesFromADManager` 1.</span><span class="sxs-lookup"><span data-stu-id="3da06-140">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3da06-141">Пример</span><span class="sxs-lookup"><span data-stu-id="3da06-141">Example</span></span>  

 <span data-ttu-id="3da06-142">В следующем примере показано, как отключить возможность переопределения параметров Fusion с помощью `<disableFusionUpdatesFromADManager>` элемента.</span><span class="sxs-lookup"><span data-stu-id="3da06-142">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3da06-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3da06-143">See also</span></span>

- [<span data-ttu-id="3da06-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="3da06-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3da06-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="3da06-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3da06-146">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="3da06-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
