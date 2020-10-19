---
title: Создание сборок
description: Узнайте как создать однофайловую или многофайловую сборку с помощью интегрированной среды разработки, например Visual Studio, либо с помощью компиляторов и средств, доступных в пакете Windows SDK.
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET], multifile
- single-file assemblies
- assemblies [.NET], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
ms.openlocfilehash: e1b08e40ae3b4c377cec52cb1ebf6db643af6429
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160585"
---
# <a name="create-assemblies"></a><span data-ttu-id="5620b-103">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="5620b-103">Create assemblies</span></span>

<span data-ttu-id="5620b-104">Однофайловую или многофайловую сборку можно создать с помощью интегрированной среды разработки, например Visual Studio, либо с помощью компиляторов и средств, доступных в Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="5620b-104">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the Windows SDK.</span></span> <span data-ttu-id="5620b-105">Простейшая сборка представляет собой один файл, имеющий простое имя и загружаемый в единственный домен приложения.</span><span class="sxs-lookup"><span data-stu-id="5620b-105">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="5620b-106">На эту сборку нельзя ссылаться из других сборок, находящихся вне папки приложения; кроме того, к ней неприменим механизм проверки версий.</span><span class="sxs-lookup"><span data-stu-id="5620b-106">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="5620b-107">Для удаления приложения, состоящего из сборки, достаточно просто удалить папку, в которой оно располагается.</span><span class="sxs-lookup"><span data-stu-id="5620b-107">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="5620b-108">Для большинства разработчиков сборки с такими возможностями достаточно для развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="5620b-108">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="5620b-109">Многофайловую сборку можно создать на основе нескольких модулей кода и файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5620b-109">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="5620b-110">Кроме того, можно создать сборку, которая будет совместно использоваться несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="5620b-110">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="5620b-111">Совместно используемая сборка должна иметь строгое имя и должна быть развернута в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="5620b-111">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="5620b-112">Существует несколько способов объединения модулей кода и ресурсов в сборки; способ зависит от следующих факторов.</span><span class="sxs-lookup"><span data-stu-id="5620b-112">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="5620b-113">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="5620b-113">Versioning</span></span>

     <span data-ttu-id="5620b-114">Объединение модулей, имеющих одни и те же сведения о версии.</span><span class="sxs-lookup"><span data-stu-id="5620b-114">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="5620b-115">Развертывание</span><span class="sxs-lookup"><span data-stu-id="5620b-115">Deployment</span></span>

     <span data-ttu-id="5620b-116">Объединение модулей кода и ресурсов, поддерживающих данную модель развертывания.</span><span class="sxs-lookup"><span data-stu-id="5620b-116">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="5620b-117">Повторное использование</span><span class="sxs-lookup"><span data-stu-id="5620b-117">Reuse</span></span>

     <span data-ttu-id="5620b-118">Объединение модулей, если они могут логически использоваться совместно для некоторых целей.</span><span class="sxs-lookup"><span data-stu-id="5620b-118">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="5620b-119">Например, сборка, состоящая из типов и классов, редко используемых для сопровождения программы, может быть помещена в ту же самую сборку.</span><span class="sxs-lookup"><span data-stu-id="5620b-119">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="5620b-120">Кроме того, типы, предназначенные для совместного использования несколькими приложениями, могут быть объединены в сборку, которая должна быть подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="5620b-120">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="5620b-121">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5620b-121">Security</span></span>

     <span data-ttu-id="5620b-122">Объединение модулей, содержащих типы, которым требуются одни и те же разрешения безопасности.</span><span class="sxs-lookup"><span data-stu-id="5620b-122">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="5620b-123">Область действия</span><span class="sxs-lookup"><span data-stu-id="5620b-123">Scoping</span></span>

     <span data-ttu-id="5620b-124">Объединение модулей, содержащих типы, область видимости которых должна быть ограничена этой же сборкой.</span><span class="sxs-lookup"><span data-stu-id="5620b-124">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="5620b-125">Особое внимание нужно уделить предоставлению доступа к сборкам среды CLR из неуправляемых COM-приложений.</span><span class="sxs-lookup"><span data-stu-id="5620b-125">There are special considerations when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="5620b-126">Дополнительные сведения о работе с неуправляемым кодом см. в разделе [Предоставление COM-клиентам доступа к компонентам .NET Framework](../../framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="5620b-126">For more information about working with unmanaged code, see [Expose .NET Framework components to COM](../../framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5620b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5620b-127">See also</span></span>

- [<span data-ttu-id="5620b-128">Управление версиями сборок</span><span class="sxs-lookup"><span data-stu-id="5620b-128">Assembly versioning</span></span>](versioning.md)
- [<span data-ttu-id="5620b-129">Практическое руководство. Создание однофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="5620b-129">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)
- [<span data-ttu-id="5620b-130">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="5620b-130">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="5620b-131">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="5620b-131">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="5620b-132">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="5620b-132">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)
