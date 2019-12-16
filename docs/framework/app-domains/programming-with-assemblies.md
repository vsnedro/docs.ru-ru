---
title: "Программирование с использованием сборок"
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
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 368021062a3ad49d2c63f92797c59b8c0f1cddfc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="programming-with-assemblies"></a><span data-ttu-id="13ac6-102">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="13ac6-102">Programming with Assemblies</span></span>
<span data-ttu-id="13ac6-103">Сборки являются структурными элементами .NET Framework. Они составляют основную единицу развертывания, управления версиями, повторного использования, областей действия активации и разрешений безопасности.</span><span class="sxs-lookup"><span data-stu-id="13ac6-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="13ac6-104">Сборка предоставляет среде CLR сведения, необходимые для распознавания реализаций типов.</span><span class="sxs-lookup"><span data-stu-id="13ac6-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="13ac6-105">Она представляет собой коллекцию типов и ресурсов, собранных для совместной работы и образующих логическую функциональную единицу.</span><span class="sxs-lookup"><span data-stu-id="13ac6-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="13ac6-106">Для среды выполнения тип не существует вне контекста сборки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="13ac6-107">В этом разделе описываются процедуры создания модулей, сборок из модулей, пары ключей, а также подписывания сборки строгим именем и установки сборки в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="13ac6-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="13ac6-108">Кроме того, в этом разделе описывается использование [дизассемблера MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) для просмотра данных манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13ac6-109">Начиная с .NET Framework версии 2.0, среда выполнения не загружает сборку, которая была скомпилирована на платформе .NET Framework, номер версии которой выше номера версии текущей загруженной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="13ac6-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="13ac6-110">Это применимо к сочетанию основного и дополнительного номеров для номера версии.</span><span class="sxs-lookup"><span data-stu-id="13ac6-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13ac6-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="13ac6-111">In This Section</span></span>  
 [<span data-ttu-id="13ac6-112">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="13ac6-112">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="13ac6-113">Содержит обзор однофайловых и многофайловых сборок.</span><span class="sxs-lookup"><span data-stu-id="13ac6-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="13ac6-114">Имена сборок</span><span class="sxs-lookup"><span data-stu-id="13ac6-114">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
 <span data-ttu-id="13ac6-115">Общие сведения об именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="13ac6-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="13ac6-116">Практическое руководство. Определение полного имени сборки</span><span class="sxs-lookup"><span data-stu-id="13ac6-116">How to: Determine an Assembly's Fully Qualified Name</span></span>](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 <span data-ttu-id="13ac6-117">Описание определения полного имени сборки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="13ac6-118">Выполнение приложений интрасети с полным доверием</span><span class="sxs-lookup"><span data-stu-id="13ac6-118">Running Intranet Applications in Full Trust</span></span>](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="13ac6-119">Описание способа указания устаревшей политики безопасности для сборок с полным доверием в общем ресурсе интрасети.</span><span class="sxs-lookup"><span data-stu-id="13ac6-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="13ac6-120">Расположение сборки</span><span class="sxs-lookup"><span data-stu-id="13ac6-120">Assembly Location</span></span>](../../../docs/framework/app-domains/assembly-location.md)  
 <span data-ttu-id="13ac6-121">Обзор мест размещения сборок.</span><span class="sxs-lookup"><span data-stu-id="13ac6-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="13ac6-122">Практическое руководство. Построение однофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="13ac6-122">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 <span data-ttu-id="13ac6-123">Описание способа создания однофайловой сборки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="13ac6-124">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="13ac6-124">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="13ac6-125">Описание причин создания многофайловых сборок.</span><span class="sxs-lookup"><span data-stu-id="13ac6-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="13ac6-126">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="13ac6-126">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 <span data-ttu-id="13ac6-127">Описание способа создания многофайловой сборки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="13ac6-128">Настройка атрибутов сборки</span><span class="sxs-lookup"><span data-stu-id="13ac6-128">Setting Assembly Attributes</span></span>](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 <span data-ttu-id="13ac6-129">Описание атрибутов сборки и способов их настройки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="13ac6-130">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="13ac6-130">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 <span data-ttu-id="13ac6-131">Описание способа и причин подписи сборки строгим именем (с перечнем практических руководств).</span><span class="sxs-lookup"><span data-stu-id="13ac6-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="13ac6-132">Отложенная подпись сборки</span><span class="sxs-lookup"><span data-stu-id="13ac6-132">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 <span data-ttu-id="13ac6-133">Описывает, как отложить подписывание сборки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="13ac6-134">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="13ac6-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="13ac6-135">Описание способа и причин добавления сборок в глобальный кэш сборок (с перечнем практических руководств).</span><span class="sxs-lookup"><span data-stu-id="13ac6-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="13ac6-136">Практическое руководство. Просмотр содержимого сборок</span><span class="sxs-lookup"><span data-stu-id="13ac6-136">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="13ac6-137">Описание использования дизассемблера MSIL (Ildasm.exe) для просмотра содержимого сборки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="13ac6-138">Переадресация типов в среде CLR</span><span class="sxs-lookup"><span data-stu-id="13ac6-138">Type Forwarding in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 <span data-ttu-id="13ac6-139">Описание использования переадресации типов для перемещения типа в другую сборку, не нарушая работу существующих приложений.</span><span class="sxs-lookup"><span data-stu-id="13ac6-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="13ac6-140">Ссылка</span><span class="sxs-lookup"><span data-stu-id="13ac6-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="13ac6-141">Класс .NET Framework, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="13ac6-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="13ac6-142">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="13ac6-142">Related Sections</span></span>  
 [<span data-ttu-id="13ac6-143">Практическое руководство. Получение сведений о типах и членах из сборки</span><span class="sxs-lookup"><span data-stu-id="13ac6-143">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="13ac6-144">Описание программного получения типа и других сведений из сборки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="13ac6-145">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="13ac6-145">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="13ac6-146">Общий обзор сборок среды CLR.</span><span class="sxs-lookup"><span data-stu-id="13ac6-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="13ac6-147">Управление версиями сборок</span><span class="sxs-lookup"><span data-stu-id="13ac6-147">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 <span data-ttu-id="13ac6-148">Общие сведения о привязке сборок и об атрибутах <xref:System.Reflection.AssemblyVersionAttribute> и <xref:System.Reflection.AssemblyInformationalVersionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="13ac6-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="13ac6-149">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="13ac6-149">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="13ac6-150">Описывается то, как среда выполнения определяет, какую сборку следует использовать для выполнения запроса привязки.</span><span class="sxs-lookup"><span data-stu-id="13ac6-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 [<span data-ttu-id="13ac6-151">Отражение</span><span class="sxs-lookup"><span data-stu-id="13ac6-151">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="13ac6-152">Использование класса **Reflection** для получения сведений о сборке.</span><span class="sxs-lookup"><span data-stu-id="13ac6-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
