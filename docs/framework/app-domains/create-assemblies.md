---
title: "Создание сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 583c448bd939cd4d1d16bff372afff4172dcf985
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="creating-assemblies"></a><span data-ttu-id="26ef8-102">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="26ef8-102">Creating Assemblies</span></span>
<span data-ttu-id="26ef8-103">Можно создать однофайловую или многофайловую сборку с помощью интегрированной среды разработки IDE, такой как [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], или с помощью компиляторов и средств, предоставляемых [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26ef8-103">You can create single-file or multifile assemblies using an IDE, such as [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], or the compilers and tools provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span> <span data-ttu-id="26ef8-104">Простейшая сборка представляет собой один файл, имеющий простое имя и загружаемый в единственный домен приложения.</span><span class="sxs-lookup"><span data-stu-id="26ef8-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="26ef8-105">На эту сборку нельзя ссылаться из других сборок, находящихся вне папки приложения; кроме того, к ней неприменим механизм проверки версий.</span><span class="sxs-lookup"><span data-stu-id="26ef8-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="26ef8-106">Для удаления приложения, состоящего из сборки, достаточно просто удалить папку, в которой оно располагается.</span><span class="sxs-lookup"><span data-stu-id="26ef8-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="26ef8-107">Для большинства разработчиков сборки с такими возможностями достаточно для развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="26ef8-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>  
  
 <span data-ttu-id="26ef8-108">Многофайловую сборку можно создать на основе нескольких модулей кода и файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="26ef8-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="26ef8-109">Кроме того, можно создать сборку, которая будет совместно использоваться несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="26ef8-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="26ef8-110">Совместно используемая сборка должна иметь строгое имя и должна быть развернута в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="26ef8-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="26ef8-111">Существует несколько способов объединения модулей кода и ресурсов в сборки; способ зависит от следующих факторов.</span><span class="sxs-lookup"><span data-stu-id="26ef8-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>  
  
-   <span data-ttu-id="26ef8-112">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="26ef8-112">Versioning</span></span>  
  
     <span data-ttu-id="26ef8-113">Объединение модулей, имеющих одни и те же сведения о версии.</span><span class="sxs-lookup"><span data-stu-id="26ef8-113">Group modules that should have the same version information.</span></span>  
  
-   <span data-ttu-id="26ef8-114">Развертывание</span><span class="sxs-lookup"><span data-stu-id="26ef8-114">Deployment</span></span>  
  
     <span data-ttu-id="26ef8-115">Объединение модулей кода и ресурсов, поддерживающих данную модель развертывания.</span><span class="sxs-lookup"><span data-stu-id="26ef8-115">Group code modules and resources that support your model of deployment.</span></span>  
  
-   <span data-ttu-id="26ef8-116">Повторное использование</span><span class="sxs-lookup"><span data-stu-id="26ef8-116">Reuse</span></span>  
  
     <span data-ttu-id="26ef8-117">Объединение модулей, если они могут логически использоваться совместно для некоторых целей.</span><span class="sxs-lookup"><span data-stu-id="26ef8-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="26ef8-118">Например, сборка, состоящая из типов и классов, редко используемых для сопровождения программы, может быть помещена в ту же самую сборку.</span><span class="sxs-lookup"><span data-stu-id="26ef8-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="26ef8-119">Кроме того, типы, предназначенные для совместного использования несколькими приложениями, могут быть объединены в сборку, которая должна быть подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="26ef8-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>  
  
-   <span data-ttu-id="26ef8-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="26ef8-120">Security</span></span>  
  
     <span data-ttu-id="26ef8-121">Объединение модулей, содержащих типы, которым требуются одни и те же разрешения безопасности.</span><span class="sxs-lookup"><span data-stu-id="26ef8-121">Group modules containing types that require the same security permissions.</span></span>  
  
-   <span data-ttu-id="26ef8-122">Область действия</span><span class="sxs-lookup"><span data-stu-id="26ef8-122">Scoping</span></span>  
  
     <span data-ttu-id="26ef8-123">Объединение модулей, содержащих типы, область видимости которых должна быть ограничена этой же сборкой.</span><span class="sxs-lookup"><span data-stu-id="26ef8-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>  
  
 <span data-ttu-id="26ef8-124">Необходимо обратить особое внимание при предоставлении доступа к сборкам среды CLR из неуправляемых COM-приложений.</span><span class="sxs-lookup"><span data-stu-id="26ef8-124">Special considerations must be made when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="26ef8-125">Дополнительные сведения о работе с неуправляемым кодом содержатся в разделе [Предоставление COM-клиентам доступа к компонентам .NET Framework](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="26ef8-125">For more information about working with unmanaged code, see [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ef8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="26ef8-126">See Also</span></span>  
 <span data-ttu-id="26ef8-127">[Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="26ef8-127">[Programming with Assemblies](../../../docs/framework/app-domains/programming-with-assemblies.md) </span></span>  
 <span data-ttu-id="26ef8-128">[Управление версиями сборок](../../../docs/framework/app-domains/assembly-versioning.md) </span><span class="sxs-lookup"><span data-stu-id="26ef8-128">[Assembly Versioning](../../../docs/framework/app-domains/assembly-versioning.md) </span></span>  
 <span data-ttu-id="26ef8-129">[Практическое руководство. Построение однофайловой сборки](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="26ef8-129">[How to: Build a Single-File Assembly](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md) </span></span>  
 <span data-ttu-id="26ef8-130">[Практическое руководство. Создание многофайловой сборки](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="26ef8-130">[How to: Build a Multifile Assembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span></span>  
 <span data-ttu-id="26ef8-131">[Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="26ef8-131">[How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span></span>  
 [<span data-ttu-id="26ef8-132">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="26ef8-132">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
