---
title: Элемент <disableCachingBindingFailures>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
ms.openlocfilehash: c9e608bfd54b641564a9095076455e10dd8653fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176127"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="ba913-102">Элемент \<disableCachingBindingFailures></span><span class="sxs-lookup"><span data-stu-id="ba913-102">\<disableCachingBindingFailures> Element</span></span>

<span data-ttu-id="ba913-103">Указывает, следует ли отключать кэширование ошибок привязки, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="ba913-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**  
  
## <a name="syntax"></a><span data-ttu-id="ba913-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba913-104">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba913-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba913-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ba913-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba913-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba913-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba913-107">Attributes</span></span>  
  
|<span data-ttu-id="ba913-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ba913-108">Attribute</span></span>|<span data-ttu-id="ba913-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ba913-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba913-110">Включено</span><span class="sxs-lookup"><span data-stu-id="ba913-110">enabled</span></span>|<span data-ttu-id="ba913-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ba913-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="ba913-112">Указывает, следует ли отключать кэширование ошибок привязки, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="ba913-112">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ba913-113">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="ba913-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="ba913-114">Значение</span><span class="sxs-lookup"><span data-stu-id="ba913-114">Value</span></span>|<span data-ttu-id="ba913-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ba913-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba913-116">0</span><span class="sxs-lookup"><span data-stu-id="ba913-116">0</span></span>|<span data-ttu-id="ba913-117">Не отключайте кэширование ошибок привязки, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="ba913-117">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="ba913-118">Это поведение привязки по умолчанию, начинающееся с .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="ba913-118">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="ba913-119">1</span><span class="sxs-lookup"><span data-stu-id="ba913-119">1</span></span>|<span data-ttu-id="ba913-120">Отключите кэширование ошибок привязки, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="ba913-120">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="ba913-121">Этот параметр восстанавливает поведение привязки .NET Framework версии 1,1.</span><span class="sxs-lookup"><span data-stu-id="ba913-121">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba913-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba913-122">Child Elements</span></span>  

 <span data-ttu-id="ba913-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ba913-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba913-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba913-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ba913-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba913-125">Element</span></span>|<span data-ttu-id="ba913-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ba913-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ba913-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ba913-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ba913-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="ba913-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba913-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba913-129">Remarks</span></span>  

 <span data-ttu-id="ba913-130">Начиная с версии .NET Framework 2,0, поведением по умолчанию для загрузки сборок является кэширование всех ошибок привязки и загрузки.</span><span class="sxs-lookup"><span data-stu-id="ba913-130">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="ba913-131">То есть если попытка загрузить сборку завершается ошибкой, последующие запросы на загрузку одной и той же сборки будут завершаться сбоем немедленно, без каких-либо попыток нахождение сборки.</span><span class="sxs-lookup"><span data-stu-id="ba913-131">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="ba913-132">Этот элемент отключает поведение по умолчанию для сбоев привязки, возникающих из-за того, что сборка не найдена в пути поиска.</span><span class="sxs-lookup"><span data-stu-id="ba913-132">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="ba913-133">Эти ошибки вызываются <xref:System.IO.FileNotFoundException> .</span><span class="sxs-lookup"><span data-stu-id="ba913-133">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="ba913-134">Этот элемент не влияет на некоторые ошибки привязки и загрузки и всегда кэшируется.</span><span class="sxs-lookup"><span data-stu-id="ba913-134">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="ba913-135">Эти сбои возникают из-за того, что сборка найдена, но не может быть загружена.</span><span class="sxs-lookup"><span data-stu-id="ba913-135">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="ba913-136">Они создают <xref:System.BadImageFormatException> или <xref:System.IO.FileLoadException> .</span><span class="sxs-lookup"><span data-stu-id="ba913-136">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="ba913-137">В следующем списке приведены некоторые примеры таких сбоев.</span><span class="sxs-lookup"><span data-stu-id="ba913-137">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="ba913-138">Если попытка загрузить файл не является допустимой сборкой, последующие попытки загрузки сборки завершатся ошибкой, даже если поврежденный файл заменяется правильной сборкой.</span><span class="sxs-lookup"><span data-stu-id="ba913-138">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="ba913-139">При попытке загрузить сборку, заблокированную файловой системой, последующие попытки загрузки сборки завершатся ошибкой даже после того, как сборка будет освобождена файловой системой.</span><span class="sxs-lookup"><span data-stu-id="ba913-139">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="ba913-140">Если одна или несколько версий сборки, которые вы пытаетесь загрузить, находятся в пути поиска, но конкретная Запрашиваемая версия не существует, последующие попытки загрузки этой версии завершатся ошибкой, даже если в путь поиска проверки перемещается правильная версия.</span><span class="sxs-lookup"><span data-stu-id="ba913-140">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba913-141">Пример</span><span class="sxs-lookup"><span data-stu-id="ba913-141">Example</span></span>  

 <span data-ttu-id="ba913-142">В следующем примере показано, как отключить кэширование ошибок привязки сборок, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="ba913-142">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba913-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ba913-143">See also</span></span>

- [<span data-ttu-id="ba913-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ba913-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ba913-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ba913-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ba913-146">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="ba913-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
