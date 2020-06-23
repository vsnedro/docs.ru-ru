---
title: Указание расположения сборки
description: См. раздел как указать расположение сборки в .NET с помощью элемента codeBase или элемента зондирования в XML-файле конфигурации.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: e14bdc12598d0aa6cdd2789b09a04ab8ed134169
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141708"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="f3d50-103">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="f3d50-103">Specifying an Assembly's Location</span></span>
<span data-ttu-id="f3d50-104">Существует два способа указания расположения сборки:</span><span class="sxs-lookup"><span data-stu-id="f3d50-104">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="f3d50-105">С помощью [\<codeBase>](./file-schema/runtime/codebase-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="f3d50-105">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="f3d50-106">С помощью [\<probing>](./file-schema/runtime/probing-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="f3d50-106">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="f3d50-107">Можно также использовать [средство настройки .NET Framework (Mscorcfg. msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) , чтобы указать расположения сборок или указать расположения среды CLR для проверки сборок.</span><span class="sxs-lookup"><span data-stu-id="f3d50-107">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="f3d50-108">Использование \<codeBase> элемента</span><span class="sxs-lookup"><span data-stu-id="f3d50-108">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="f3d50-109">Элемент можно использовать **\<codeBase>** только в конфигурации компьютера или в файлах политики издателя, которые также перенаправляют версию сборки.</span><span class="sxs-lookup"><span data-stu-id="f3d50-109">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="f3d50-110">Когда среда выполнения определяет используемую версию сборки, она применяет параметр базы кода из файла, который определяет версию.</span><span class="sxs-lookup"><span data-stu-id="f3d50-110">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="f3d50-111">Если не указано ни одной базы кода, среда выполнения проверяет наличие сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="f3d50-111">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="f3d50-112">Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="f3d50-112">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="f3d50-113">В следующем примере показано, как указать расположение сборки.</span><span class="sxs-lookup"><span data-stu-id="f3d50-113">The following example shows how to specify an assembly's location.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="f3d50-114">Атрибут **Version** необходим для всех сборок со строгими именами, но должен быть опущен для сборок, не имеющих строгих имен.</span><span class="sxs-lookup"><span data-stu-id="f3d50-114">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="f3d50-115">**\<codeBase>** Элементу требуется атрибут **href** .</span><span class="sxs-lookup"><span data-stu-id="f3d50-115">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="f3d50-116">В элементе нельзя указывать диапазоны версий **\<codeBase>** .</span><span class="sxs-lookup"><span data-stu-id="f3d50-116">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3d50-117">Если вы предоставляете указание базы кода для сборки, не имеющей строгого имени, подсказка должна указывать на базу приложения или подкаталог базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="f3d50-117">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="f3d50-118">Использование \<probing> элемента</span><span class="sxs-lookup"><span data-stu-id="f3d50-118">Using the \<probing> Element</span></span>  
 <span data-ttu-id="f3d50-119">Среда выполнения находит сборки, не имеющие базы кода, путем проверки.</span><span class="sxs-lookup"><span data-stu-id="f3d50-119">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="f3d50-120">Дополнительные сведения о проверке см. в разделе [как среда выполнения находит сборки](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="f3d50-120">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="f3d50-121">[\<probing>](./file-schema/runtime/probing-element.md)Элемент в файле конфигурации приложения можно использовать для указания подкаталогов, которые среда выполнения должна искать при поиске сборки.</span><span class="sxs-lookup"><span data-stu-id="f3d50-121">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="f3d50-122">В следующем примере показано, как указать каталоги, которые должна искать среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3d50-122">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="f3d50-123">Атрибут **privatePath** содержит каталоги, в которых среда выполнения должна искать сборки.</span><span class="sxs-lookup"><span data-stu-id="f3d50-123">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="f3d50-124">Если приложение расположено в папке C:\Program Files\MyApp, среда выполнения будет искать сборки, не указывающие базу кода в C:\Program Филес\мяпп\бин, C:\Program Files\MyApp\Bin2\Subbin и C:\Program Files\MyApp\Bin3.</span><span class="sxs-lookup"><span data-stu-id="f3d50-124">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="f3d50-125">Каталоги, указанные в параметре **privatePath** , должны быть подкаталогами базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="f3d50-125">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d50-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f3d50-126">See also</span></span>

- [<span data-ttu-id="f3d50-127">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="f3d50-127">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="f3d50-128">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="f3d50-128">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="f3d50-129">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="f3d50-129">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="f3d50-130">Настройка приложений с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="f3d50-130">Configuring Apps by using Configuration Files</span></span>](index.md)
