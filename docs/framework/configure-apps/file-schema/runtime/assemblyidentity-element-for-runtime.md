---
title: Элемент <assemblyIdentity> для <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154313"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="abc46-102">Элемент \<assemblyIdentity> для \<runtime></span><span class="sxs-lookup"><span data-stu-id="abc46-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="abc46-103">Содержит идентифицирующие сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="abc46-103">Contains identifying information about the assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**  
  
## <a name="syntax"></a><span data-ttu-id="abc46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abc46-104">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abc46-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="abc46-105">Attributes and Elements</span></span>  
 <span data-ttu-id="abc46-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="abc46-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abc46-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="abc46-107">Attributes</span></span>  
  
|<span data-ttu-id="abc46-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="abc46-108">Attribute</span></span>|<span data-ttu-id="abc46-109">Описание</span><span class="sxs-lookup"><span data-stu-id="abc46-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="abc46-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="abc46-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="abc46-111">Имя сборки</span><span class="sxs-lookup"><span data-stu-id="abc46-111">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="abc46-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="abc46-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="abc46-113">Строка, указывающая язык и страну или регион сборки.</span><span class="sxs-lookup"><span data-stu-id="abc46-113">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="abc46-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="abc46-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="abc46-115">Шестнадцатеричное значение, указывающее строгое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="abc46-115">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="abc46-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="abc46-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="abc46-117">Одно из значений "x86", "amd64", "MSIL" или "ia64", определяющее архитектуру процессора для сборки, содержащей код, зависящий от процессора.</span><span class="sxs-lookup"><span data-stu-id="abc46-117">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="abc46-118">В значениях регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="abc46-118">The values are not case-sensitive.</span></span> <span data-ttu-id="abc46-119">Если атрибуту присвоено любое другое значение, весь `<assemblyIdentity>` элемент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="abc46-119">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="abc46-120">См. раздел <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="abc46-120">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="abc46-121">Атрибут processorArchitecture</span><span class="sxs-lookup"><span data-stu-id="abc46-121">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="abc46-122">Значение</span><span class="sxs-lookup"><span data-stu-id="abc46-122">Value</span></span>|<span data-ttu-id="abc46-123">Описание</span><span class="sxs-lookup"><span data-stu-id="abc46-123">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="abc46-124">Только архитектура AMD x86-64.</span><span class="sxs-lookup"><span data-stu-id="abc46-124">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="abc46-125">Только архитектура Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="abc46-125">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="abc46-126">Код нейтрален по отношению к процессору и разрядности слова.</span><span class="sxs-lookup"><span data-stu-id="abc46-126">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="abc46-127">32-разрядный процессор x86, либо собственный, либо в среде Windows on Windows (WOW) на 64-разрядной платформе.</span><span class="sxs-lookup"><span data-stu-id="abc46-127">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abc46-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="abc46-128">Child Elements</span></span>  
 <span data-ttu-id="abc46-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="abc46-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abc46-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="abc46-130">Parent Elements</span></span>  
  
|<span data-ttu-id="abc46-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="abc46-131">Element</span></span>|<span data-ttu-id="abc46-132">Описание</span><span class="sxs-lookup"><span data-stu-id="abc46-132">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="abc46-133">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="abc46-133">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="abc46-134">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="abc46-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="abc46-135">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="abc46-135">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="abc46-136">`<dependentAssembly>`Для каждой сборки используется один элемент.</span><span class="sxs-lookup"><span data-stu-id="abc46-136">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="abc46-137">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="abc46-137">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abc46-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="abc46-138">Remarks</span></span>  
 <span data-ttu-id="abc46-139">Каждый **\<dependentAssembly>** элемент должен иметь один **\<assemblyIdentity>** дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="abc46-139">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="abc46-140">Если `processorArchitecture` атрибут имеется, `<assemblyIdentity>` элемент применяется только к сборке с соответствующей архитектурой процессора.</span><span class="sxs-lookup"><span data-stu-id="abc46-140">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="abc46-141">Если `processorArchitecture` атрибут отсутствует, `<assemblyIdentity>` элемент может применяться к сборке с любой архитектурой процессора.</span><span class="sxs-lookup"><span data-stu-id="abc46-141">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="abc46-142">В следующем примере показан файл конфигурации для двух сборок с одинаковым именем, предназначенных для двух разных архитектур процессора, чьи версии не поддерживали синхронизацию. При выполнении приложения на платформе x86 первый `<assemblyIdentity>` элемент применяется, а другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="abc46-142">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="abc46-143">Если приложение выполняется на платформе, отличной от x86 или ia64, то оба они игнорируются.</span><span class="sxs-lookup"><span data-stu-id="abc46-143">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="abc46-144">Если файл конфигурации содержит элемент без `<assemblyIdentity>` `processorArchitecture` атрибута и не содержит элемент, соответствующий платформе, то используется элемент без `processorArchitecture` атрибута.</span><span class="sxs-lookup"><span data-stu-id="abc46-144">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abc46-145">Пример</span><span class="sxs-lookup"><span data-stu-id="abc46-145">Example</span></span>  
 <span data-ttu-id="abc46-146">В следующем примере показано, как предоставить сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="abc46-146">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="abc46-147">См. также</span><span class="sxs-lookup"><span data-stu-id="abc46-147">See also</span></span>

- [<span data-ttu-id="abc46-148">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="abc46-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="abc46-149">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="abc46-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="abc46-150">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="abc46-150">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
