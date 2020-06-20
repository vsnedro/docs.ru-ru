---
title: Практическое руководство. Поиск сборок с помощью DEVPATH
description: Проверьте, правильно ли работает общая сборка с множеством приложений в .NET, используя файл конфигурации компьютера XML и переменную среды DEVPATH.
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 50b61eedddabd660b1834565a61738f460ae9ff9
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105374"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="82eab-103">Практическое руководство. Поиск сборок с помощью DEVPATH</span><span class="sxs-lookup"><span data-stu-id="82eab-103">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="82eab-104">Разработчикам может потребоваться убедиться, что создаваемая ими общая сборка работает правильно с несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="82eab-104">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="82eab-105">Вместо постоянного размещения сборки в глобальном кэше сборок во время цикла разработки разработчик может создать переменную среды DEVPATH, которая указывает на выходной каталог сборки для сборки.</span><span class="sxs-lookup"><span data-stu-id="82eab-105">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="82eab-106">Например, предположим, что создается общая сборка с именем Мишаредассембли, а выходной каталог — К:\мишаредассембли\дебуг.</span><span class="sxs-lookup"><span data-stu-id="82eab-106">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="82eab-107">К:\мишаредассембли\дебуг можно разместить в переменной DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="82eab-107">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="82eab-108">Затем необходимо указать [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) элемент в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="82eab-108">You must then specify the [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="82eab-109">Этот элемент указывает среде CLR использовать DEVPATH для нахождение сборок.</span><span class="sxs-lookup"><span data-stu-id="82eab-109">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="82eab-110">Общая сборка должна быть обнаружена средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="82eab-110">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="82eab-111">Чтобы указать частный каталог для разрешения ссылок на сборки, используйте [ \<codeBase> элемент](./file-schema/runtime/codebase-element.md) или [ \<probing> элемент](./file-schema/runtime/probing-element.md) в файле конфигурации, как описано в разделе [Указание расположения сборки](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="82eab-111">To specify a private directory for resolving assembly references use the [\<codeBase> Element](./file-schema/runtime/codebase-element.md) or [\<probing> Element](./file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>  <span data-ttu-id="82eab-112">Также можно разместить сборку в подкаталоге каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="82eab-112">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="82eab-113">Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="82eab-113">For more information, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82eab-114">Это дополнительная функция, предназначенная только для разработки.</span><span class="sxs-lookup"><span data-stu-id="82eab-114">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="82eab-115">В следующем примере показано, как заставить среду выполнения искать сборки в каталогах, заданных переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="82eab-115">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82eab-116">Пример</span><span class="sxs-lookup"><span data-stu-id="82eab-116">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="82eab-117">По умолчанию этот параметр имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="82eab-117">This setting defaults to false.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82eab-118">Используйте этот параметр только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="82eab-118">Use this setting only at development time.</span></span> <span data-ttu-id="82eab-119">Среда выполнения не проверяет версии сборок со строгими именами, найденных в DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="82eab-119">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="82eab-120">Он просто использует первую найденную сборку.</span><span class="sxs-lookup"><span data-stu-id="82eab-120">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82eab-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="82eab-121">See also</span></span>

- [<span data-ttu-id="82eab-122">Настройка приложений с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="82eab-122">Configuring Apps by using Configuration Files</span></span>](index.md)
