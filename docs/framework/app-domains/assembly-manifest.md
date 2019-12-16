---
title: "Манифест сборки"
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
- assembly manifest
- dynamic assemblies, assembly manifest
- metadata, assembly manifest
- culture, assembly manifest
- assemblies [.NET Framework], metadata
ms.assetid: 8e40fab9-549d-4731-aec2-ffa47a382de0
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eb20bfac6717779f5394724617d247a6dc980c7e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="assembly-manifest"></a><span data-ttu-id="5ff7d-102">Манифест сборки</span><span class="sxs-lookup"><span data-stu-id="5ff7d-102">Assembly Manifest</span></span>
<span data-ttu-id="5ff7d-103">Любая сборка, статическая или динамическая, содержит коллекцию данных с описанием того, как ее элементы связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-103">Every assembly, whether static or dynamic, contains a collection of data that describes how the elements in the assembly relate to each other.</span></span> <span data-ttu-id="5ff7d-104">Эти метаданные содержатся в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-104">The assembly manifest contains this assembly metadata.</span></span> <span data-ttu-id="5ff7d-105">Манифест сборки содержит все метаданные, необходимые для задания требований сборки к версиям и удостоверения безопасности, а также все метаданные, необходимые для определения области действия сборки и разрешения ссылок на ресурсы и классы.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-105">An assembly manifest contains all the metadata needed to specify the assembly's version requirements and security identity, and all metadata needed to define the scope of the assembly and resolve references to resources and classes.</span></span> <span data-ttu-id="5ff7d-106">Манифест сборки может храниться в PE-файле (EXE или DLL) с кодом MSIL или же в отдельном PE-файле, содержащем только данные манифеста.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-106">The assembly manifest can be stored in either a PE file (an .exe or .dll) with Microsoft intermediate language (MSIL) code or in a standalone PE file that contains only assembly manifest information.</span></span>  
  
 <span data-ttu-id="5ff7d-107">На следующей иллюстрации показаны различные способы хранения манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-107">The following illustration shows the different ways the manifest can be stored.</span></span>  
  
 <span data-ttu-id="5ff7d-108">![Сборка из одного файла](../../../docs/framework/app-domains/media/assemblytypes.gif "assemblytypes")</span><span class="sxs-lookup"><span data-stu-id="5ff7d-108">![A single&#45;file assembly](../../../docs/framework/app-domains/media/assemblytypes.gif "assemblytypes")</span></span>  
<span data-ttu-id="5ff7d-109">Типы сборок</span><span class="sxs-lookup"><span data-stu-id="5ff7d-109">Types of assemblies</span></span>  
  
 <span data-ttu-id="5ff7d-110">Для сборки с одним связанным файлом манифест включается в PE-файл, чтобы получить однофайловую сборку.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-110">For an assembly with one associated file, the manifest is incorporated into the PE file to form a single-file assembly.</span></span> <span data-ttu-id="5ff7d-111">Создать многофайловую сборку можно, включив в нее отдельный файл манифеста или же добавив манифест в один из PE-файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-111">You can create a multifile assembly with a standalone manifest file or with the manifest incorporated into one of the PE files in the assembly.</span></span>  
  
 <span data-ttu-id="5ff7d-112">Манифест сборки предназначен для следующих задач:</span><span class="sxs-lookup"><span data-stu-id="5ff7d-112">Each assembly's manifest performs the following functions:</span></span>  
  
-   <span data-ttu-id="5ff7d-113">перечисление файлов, составляющих сборку;</span><span class="sxs-lookup"><span data-stu-id="5ff7d-113">Enumerates the files that make up the assembly.</span></span>  
  
-   <span data-ttu-id="5ff7d-114">сопоставление ссылок на типы и ресурсы сборки с файлами, содержащими объявления и реализации этих типов и ресурсов;</span><span class="sxs-lookup"><span data-stu-id="5ff7d-114">Governs how references to the assembly's types and resources map to the files that contain their declarations and implementations.</span></span>  
  
-   <span data-ttu-id="5ff7d-115">перечисление других сборок, от которых зависит эта сборка;</span><span class="sxs-lookup"><span data-stu-id="5ff7d-115">Enumerates other assemblies on which the assembly depends.</span></span>  
  
-   <span data-ttu-id="5ff7d-116">обеспечение косвенного обращения пользователей сборки к подробностям ее реализации;</span><span class="sxs-lookup"><span data-stu-id="5ff7d-116">Provides a level of indirection between consumers of the assembly and the assembly's implementation details.</span></span>  
  
-   <span data-ttu-id="5ff7d-117">предоставление собственного описания сборки;</span><span class="sxs-lookup"><span data-stu-id="5ff7d-117">Renders the assembly self-describing.</span></span>  
  
## <a name="assembly-manifest-contents"></a><span data-ttu-id="5ff7d-118">Содержание манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="5ff7d-118">Assembly Manifest Contents</span></span>  
 <span data-ttu-id="5ff7d-119">В следующей таблице показаны данные, содержащиеся в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-119">The following table shows the information contained in the assembly manifest.</span></span> <span data-ttu-id="5ff7d-120">Первые четыре элемента — имя сборки, номер версии, язык и региональные параметры и данные строгого имени — составляют удостоверение сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-120">The first four items—the assembly name, version number, culture, and strong name information—make up the assembly's identity.</span></span>  
  
|<span data-ttu-id="5ff7d-121">Сведения</span><span class="sxs-lookup"><span data-stu-id="5ff7d-121">Information</span></span>|<span data-ttu-id="5ff7d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="5ff7d-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5ff7d-123">Имя сборки</span><span class="sxs-lookup"><span data-stu-id="5ff7d-123">Assembly name</span></span>|<span data-ttu-id="5ff7d-124">Текстовая строка, задающая имя сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-124">A text string specifying the assembly's name.</span></span>|  
|<span data-ttu-id="5ff7d-125">Номер версии</span><span class="sxs-lookup"><span data-stu-id="5ff7d-125">Version number</span></span>|<span data-ttu-id="5ff7d-126">Основной и дополнительный номера версии, номер редакции и номер построения.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-126">A major and minor version number, and a revision and build number.</span></span> <span data-ttu-id="5ff7d-127">Среда CLR использует их для применения политики управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-127">The common language runtime uses these numbers to enforce version policy.</span></span>|  
|<span data-ttu-id="5ff7d-128">Язык и региональные параметры</span><span class="sxs-lookup"><span data-stu-id="5ff7d-128">Culture</span></span>|<span data-ttu-id="5ff7d-129">Сведения о поддерживаемых сборкой языке или региональных параметрах.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-129">Information on the culture or language the assembly supports.</span></span> <span data-ttu-id="5ff7d-130">Эти сведения должны использоваться только для назначения сборки в качестве сопутствующей сборки, содержащей сведения о языке или региональных параметрах</span><span class="sxs-lookup"><span data-stu-id="5ff7d-130">This information should be used only to designate an assembly as a satellite assembly containing culture- or language-specific information.</span></span> <span data-ttu-id="5ff7d-131">(сборка, содержащая сведения о языке и региональных параметрах, автоматически считается сопутствующей).</span><span class="sxs-lookup"><span data-stu-id="5ff7d-131">(An assembly with culture information is automatically assumed to be a satellite assembly.)</span></span>|  
|<span data-ttu-id="5ff7d-132">Данные о строгом имени</span><span class="sxs-lookup"><span data-stu-id="5ff7d-132">Strong name information</span></span>|<span data-ttu-id="5ff7d-133">Открытый ключ издателя, если для сборки задано строгое имя.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-133">The public key from the publisher if the assembly has been given a strong name.</span></span>|  
|<span data-ttu-id="5ff7d-134">Список всех файлов сборки</span><span class="sxs-lookup"><span data-stu-id="5ff7d-134">List of all files in the assembly</span></span>|<span data-ttu-id="5ff7d-135">Хэш и имя каждого входящего в сборку файла.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-135">A hash of each file contained in the assembly and a file name.</span></span> <span data-ttu-id="5ff7d-136">Обратите внимание, что все входящие в сборку файлы должны находиться в той же папке, что и файл с манифестом сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-136">Note that all files that make up the assembly must be in the same directory as the file containing the assembly manifest.</span></span>|  
|<span data-ttu-id="5ff7d-137">Сведения о ссылках на типы</span><span class="sxs-lookup"><span data-stu-id="5ff7d-137">Type reference information</span></span>|<span data-ttu-id="5ff7d-138">Сведения, используемые средой выполнения для сопоставления ссылок на типы с файлами, содержащими их объявления и реализации.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-138">Information used by the runtime to map a type reference to the file that contains its declaration and implementation.</span></span> <span data-ttu-id="5ff7d-139">Это касается типов, которые экспортируются сборкой.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-139">This is used for types that are exported from the assembly.</span></span>|  
|<span data-ttu-id="5ff7d-140">Сведения о ссылках на сборки</span><span class="sxs-lookup"><span data-stu-id="5ff7d-140">Information on referenced assemblies</span></span>|<span data-ttu-id="5ff7d-141">Список других сборок, на которые имеются статические ссылки из данной сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-141">A list of other assemblies that are statically referenced by the assembly.</span></span> <span data-ttu-id="5ff7d-142">Каждая ссылка включает в себя имя зависимой сборки, метаданные сборки (версию, язык и региональные параметры, операционную систему и т.д.) и открытый ключ, если у сборки есть строгое имя.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-142">Each reference includes the dependent assembly's name, assembly metadata (version, culture, operating system, and so on), and public key, if the assembly is strong named.</span></span>|  
  
 <span data-ttu-id="5ff7d-143">С помощью задания атрибутов сборки в коде можно добавить или изменить некоторые данные в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-143">You can add or change some information in the assembly manifest by using assembly attributes in your code.</span></span> <span data-ttu-id="5ff7d-144">Можно изменить данные о версии и информационные атрибуты, включая сведения о товарном знаке, авторском праве, продукте, компании и информационной версии.</span><span class="sxs-lookup"><span data-stu-id="5ff7d-144">You can change version information and informational attributes, including Trademark, Copyright, Product, Company, and Informational Version.</span></span> <span data-ttu-id="5ff7d-145">Полный список атрибутов сборки см. в разделе [Настройка атрибутов сборки](../../../docs/framework/app-domains/set-assembly-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="5ff7d-145">For a complete list of assembly attributes, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff7d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="5ff7d-146">See Also</span></span>  
 <span data-ttu-id="5ff7d-147">[Содержимое сборок](../../../docs/framework/app-domains/assembly-contents.md) </span><span class="sxs-lookup"><span data-stu-id="5ff7d-147">[Assembly Contents](../../../docs/framework/app-domains/assembly-contents.md) </span></span>  
 <span data-ttu-id="5ff7d-148">[Управление версиями сборок](../../../docs/framework/app-domains/assembly-versioning.md) </span><span class="sxs-lookup"><span data-stu-id="5ff7d-148">[Assembly Versioning](../../../docs/framework/app-domains/assembly-versioning.md) </span></span>  
 <span data-ttu-id="5ff7d-149">[Создание вспомогательных сборок](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md) </span><span class="sxs-lookup"><span data-stu-id="5ff7d-149">[Creating Satellite Assemblies](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md) </span></span>  
 [<span data-ttu-id="5ff7d-150">Сборки со строгими именами</span><span class="sxs-lookup"><span data-stu-id="5ff7d-150">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)
