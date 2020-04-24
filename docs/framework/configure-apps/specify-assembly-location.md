---
title: Указание расположения сборки
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646036"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="fdb59-102">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="fdb59-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="fdb59-103">Существует два способа указать местоположение сборки:</span><span class="sxs-lookup"><span data-stu-id="fdb59-103">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="fdb59-104">Использование [ \<элемента codeBase>.](./file-schema/runtime/codebase-element.md)</span><span class="sxs-lookup"><span data-stu-id="fdb59-104">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="fdb59-105">Использование [ \<элемента зондирования>.](./file-schema/runtime/probing-element.md)</span><span class="sxs-lookup"><span data-stu-id="fdb59-105">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="fdb59-106">Вы также можете использовать [инструмент конфигурации рамочной конфигурации .NET (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) для указания местоположений сборки или указания местоположений для общего времени выполнения языка для зондирования сборок.</span><span class="sxs-lookup"><span data-stu-id="fdb59-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="fdb59-107">Использование \<codeBase> Элемент</span><span class="sxs-lookup"><span data-stu-id="fdb59-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="fdb59-108">Элемент \*\* \<codeBase\*\* можно использовать>только в конфигурации машины или файлах политики издателя, которые также перенаправляют сборочную версию.</span><span class="sxs-lookup"><span data-stu-id="fdb59-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="fdb59-109">Когда время выполнения определяет, какую сборочную версию использовать, он применяет настройки базы кода из файла, определяющего версию.</span><span class="sxs-lookup"><span data-stu-id="fdb59-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="fdb59-110">Если кодовая база не указана, зонды времени выполнения для сборки в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="fdb59-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="fdb59-111">Для получения подробной информации, [см.](../deployment/how-the-runtime-locates-assemblies.md)</span><span class="sxs-lookup"><span data-stu-id="fdb59-111">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="fdb59-112">В следующем примере показано, как указать местоположение сборки.</span><span class="sxs-lookup"><span data-stu-id="fdb59-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="fdb59-113">Атрибут **версии** необходим для всех сильных собраний, но должен быть опущен для сборок, которые не являются сильными.</span><span class="sxs-lookup"><span data-stu-id="fdb59-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="fdb59-114">Элемент \*\* \<codeBase>\*\* требует атрибута **href.**</span><span class="sxs-lookup"><span data-stu-id="fdb59-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="fdb59-115">Вы не можете указать диапазоны версий в \*\* \<элементе codeBase>.\*\*</span><span class="sxs-lookup"><span data-stu-id="fdb59-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdb59-116">Если вы поставляете подсказку базы кода для сборки, которая не имеет сильного названия, подсказка должна указывать на базу приложений или субдиректорию базового каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="fdb59-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="fdb59-117">Использование \<зондирования> элемента</span><span class="sxs-lookup"><span data-stu-id="fdb59-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="fdb59-118">Время выполнения находит сборки, которые не имеют кодовой базы путем зондирования.</span><span class="sxs-lookup"><span data-stu-id="fdb59-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="fdb59-119">Для получения дополнительной информации о зондирования, см [Как Runtime находит сборки](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="fdb59-119">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="fdb59-120">Элемент [ \<зондирования>](./file-schema/runtime/probing-element.md) в файле конфигурации приложения можно указать субдиректорам, которые необходимо искать при поиске сборки.</span><span class="sxs-lookup"><span data-stu-id="fdb59-120">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="fdb59-121">В следующем примере показано, как указать каталоги, которые необходимо искать в времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="fdb59-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="fdb59-122">Атрибут **privatePath** содержит каталоги, которые время выполнения должно искать сборки.</span><span class="sxs-lookup"><span data-stu-id="fdb59-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="fdb59-123">Если приложение находится на C: «Программные файлы»MyApp, время выполнения будет искать сборки, которые не указывают кодовую базу в C: «Программные файлы»MyApp-Bin, C: «Программные файлы» (MyApp2)Subbin и C:»Программные файлы »MyApp»Bin3.</span><span class="sxs-lookup"><span data-stu-id="fdb59-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="fdb59-124">Каталоги, указанные в **privatePath,** должны быть субдиректорами базового каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="fdb59-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb59-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fdb59-125">See also</span></span>

- [<span data-ttu-id="fdb59-126">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="fdb59-126">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="fdb59-127">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="fdb59-127">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="fdb59-128">Как Время выполнения находит сборки</span><span class="sxs-lookup"><span data-stu-id="fdb59-128">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="fdb59-129">Настройка приложений с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="fdb59-129">Configuring Apps by using Configuration Files</span></span>](index.md)
