---
title: "Имена сборок"
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
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7029fb2b436c9ba49f2dfd3da07c5147222fbeaf
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="assembly-names"></a><span data-ttu-id="525ae-102">Имена сборок</span><span class="sxs-lookup"><span data-stu-id="525ae-102">Assembly Names</span></span>
<span data-ttu-id="525ae-103">Имя сборки хранится в метаданных и в значительной степени влияет на ее область определения и использование в приложениях.</span><span class="sxs-lookup"><span data-stu-id="525ae-103">An assembly's name is stored in metadata and has a significant impact on the assembly's scope and use by an application.</span></span> <span data-ttu-id="525ae-104">Сборки со строгим именем имеют полное имя, в состав которого входит имя сборки, язык и региональные параметры, открытый ключ и номер версии.</span><span class="sxs-lookup"><span data-stu-id="525ae-104">A strong-named assembly has a fully qualified name that includes the assembly's name, culture, public key, and version number.</span></span> <span data-ttu-id="525ae-105">Оно часто называется отображаемым именем; у загружаемых сборок его можно получить через свойство <xref:System.Reflection.Assembly.FullName%2A>.</span><span class="sxs-lookup"><span data-stu-id="525ae-105">This is frequently referred to as the display name, and for loaded assemblies can be obtained by using the <xref:System.Reflection.Assembly.FullName%2A> property.</span></span>  
  
 <span data-ttu-id="525ae-106">Среда выполнения использует эти сведения для обнаружения сборки и для того, чтобы отличать данную сборку от других сборок с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="525ae-106">The runtime uses this information to locate the assembly and differentiate it from other assemblies with the same name.</span></span> <span data-ttu-id="525ae-107">Например, сборка со строгим именем `myTypes` может иметь следующее полное имя:</span><span class="sxs-lookup"><span data-stu-id="525ae-107">For example, a strong-named assembly called `myTypes` could have the following fully qualified name:</span></span>  
  
```  
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil  
```  
  
> [!NOTE]
>  <span data-ttu-id="525ae-108">Для поддержки сборок, привязанных к конкретным процессорам, в идентификации сборки в платформе .NET Framework версии 2.0 указывается архитектура процессора.</span><span class="sxs-lookup"><span data-stu-id="525ae-108">Processor architecture is added to the assembly identity in the .NET Framework version 2.0, to allow processor-specific versions of assemblies.</span></span> <span data-ttu-id="525ae-109">Можно создавать версии сборок, идентификации которых различаются только архитектурой процессора — например 32-разрядные и 64-разрядные версии.</span><span class="sxs-lookup"><span data-stu-id="525ae-109">You can create versions of an assembly whose identity differs only by processor architecture, for example 32-bit and 64-bit processor-specific versions.</span></span> <span data-ttu-id="525ae-110">При строгом именовании указывать архитектуру процессора не требуется.</span><span class="sxs-lookup"><span data-stu-id="525ae-110">Processor architecture is not required for strong names.</span></span> <span data-ttu-id="525ae-111">Для получения дополнительной информации см. <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="525ae-111">For more information, see <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="525ae-112">В этом примере полное имя указывает, что у сборки `myTypes` имеется строгое имя с маркером общего ключа, значение языка и региональных параметров "Английский (США)" и номер версии 1.0.1234.0.</span><span class="sxs-lookup"><span data-stu-id="525ae-112">In this example, the fully qualified name indicates that the `myTypes` assembly has a strong name with a public key token, has the culture value for US English, and has a version number of 1.0.1234.0.</span></span> <span data-ttu-id="525ae-113">Архитектурой процессора является "msil", что означает, что должна выполняться JIT-компиляция в 32- или 64-разрядный код в зависимости от операционной системы и процессора.</span><span class="sxs-lookup"><span data-stu-id="525ae-113">Its processor architecture is "msil", which means that it will be just-in-time (JIT)-compiled to 32-bit code or 64-bit code depending on the operating system and processor.</span></span>  
  
 <span data-ttu-id="525ae-114">Код, запрашивающий типы в сборке, должен использовать полное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="525ae-114">Code that requests types in an assembly must use a fully qualified assembly name.</span></span> <span data-ttu-id="525ae-115">Данный подход называется полной привязкой.</span><span class="sxs-lookup"><span data-stu-id="525ae-115">This is called fully qualified binding.</span></span> <span data-ttu-id="525ae-116">Частичная привязка, при которой задается только имя самой сборки, при ссылке на сборки в платформе .NET Framework не допускается.</span><span class="sxs-lookup"><span data-stu-id="525ae-116">Partial binding, which specifies only an assembly name, is not permitted when referencing assemblies in the .NET Framework.</span></span>  
  
 <span data-ttu-id="525ae-117">Все ссылки на сборки, составляющие .NET Framework, должны содержать полное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="525ae-117">All assembly references to assemblies that make up the .NET Framework also must contain a fully qualified name of the assembly.</span></span> <span data-ttu-id="525ae-118">Например, для ссылки на сборку System.Data в .NET Framework версии 1.0 необходимо использовать следующее имя:</span><span class="sxs-lookup"><span data-stu-id="525ae-118">For example, to reference the System.Data .NET Framework assembly for version 1.0 would include:</span></span>  
  
```  
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
```  
  
 <span data-ttu-id="525ae-119">Обратите внимание, что версия соответствует номеру версии всех сборок .NET Framework, поставлявшихся с .NET Framework версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="525ae-119">Note that the version corresponds to the version number of all .NET Framework assemblies that shipped with .NET Framework version 1.0.</span></span> <span data-ttu-id="525ae-120">Для сборок .NET Framework значение языка и региональных параметров всегда нейтрально, а открытый ключ совпадает с показанным в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="525ae-120">For .NET Framework assemblies, the culture value is always neutral, and the public key is the same as shown in the above example.</span></span>  
  
 <span data-ttu-id="525ae-121">Например, при установке слушателя трассировки для добавления ссылки на сборку в файле конфигурации необходимо использовать полное имя системной сборки .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="525ae-121">For example, to add an assembly reference in a configuration file to set up a trace listener, you would include the fully qualified name of the system .NET Framework assembly:</span></span>  
  
```xml  
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
```  
  
> [!NOTE]
>  <span data-ttu-id="525ae-122">В ходе привязки среда выполнения не различает регистр в именах сборок, но при этом сохраняет его без изменений.</span><span class="sxs-lookup"><span data-stu-id="525ae-122">The runtime treats assembly names as case-insensitive when binding to an assembly, but preserves whatever case is used in an assembly name.</span></span> <span data-ttu-id="525ae-123">Ряд средств [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] работает с именами сборок с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="525ae-123">Several tools in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] handle assembly names as case-sensitive.</span></span> <span data-ttu-id="525ae-124">Оптимальным является такой порядок использования имен сборок, при котором они рассматриваются как регистрозависимые.</span><span class="sxs-lookup"><span data-stu-id="525ae-124">For best results, manage assembly names as though they were case-sensitive.</span></span>  
  
## <a name="naming-application-components"></a><span data-ttu-id="525ae-125">Правила именования компонентов приложений</span><span class="sxs-lookup"><span data-stu-id="525ae-125">Naming Application Components</span></span>  
 <span data-ttu-id="525ae-126">При определении идентификации сборки среда выполнения не учитывает имя файла.</span><span class="sxs-lookup"><span data-stu-id="525ae-126">The runtime does not consider the file name when determining an assembly's identity.</span></span> <span data-ttu-id="525ae-127">Удостоверение сборки, которое состоит из ее имени, версии, языка и региональных параметров, а также строгого имени, должно восприниматься средой выполнения однозначно.</span><span class="sxs-lookup"><span data-stu-id="525ae-127">The assembly identity, which consists of the assembly name, version, culture, and strong name, must be clear to the runtime.</span></span>  
  
 <span data-ttu-id="525ae-128">Если, к примеру, сборка с именем myAssembly.exe ссылается на сборку с именем myAssembly.dll, то при вызове myAssembly.exe привязка пройдет корректно.</span><span class="sxs-lookup"><span data-stu-id="525ae-128">For example, if you have an assembly called myAssembly.exe that references an assembly called myAssembly.dll, binding occurs correctly if you execute myAssembly.exe.</span></span> <span data-ttu-id="525ae-129">Тем не менее, если другое приложение вызовет myAssembly.exe с помощью метода <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=fullName>, при обработке запроса на привязку к сборке "myAssembly", поступившего от myAssembly.exe, среда выполнения определит, что сборка с именем "myAssembly" уже загружена.</span><span class="sxs-lookup"><span data-stu-id="525ae-129">However, if another application executes myAssembly.exe using the method <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=fullName>, the runtime determines that "myAssembly" is already loaded when myAssembly.exe requests binding to "myAssembly."</span></span> <span data-ttu-id="525ae-130">В этом случае сборка myAssembly.dll загружаться не будет.</span><span class="sxs-lookup"><span data-stu-id="525ae-130">In this case, myAssembly.dll is never loaded.</span></span> <span data-ttu-id="525ae-131">Так как запрашиваемый тип отсутствует в myAssembly.exe, то возникнет исключение <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="525ae-131">Because myAssembly.exe does not contain the requested type , a <xref:System.TypeLoadException> occurs.</span></span>  
  
 <span data-ttu-id="525ae-132">Во избежание этой проблемы необходимо следить за тем, чтобы сборки, составляющие приложение, имели разные имена, а сборки с одинаковыми именами располагались бы в разных каталогах.</span><span class="sxs-lookup"><span data-stu-id="525ae-132">To avoid this problem, make sure the assemblies that make up your application do not have the same assembly name or place assemblies with the same name in different directories.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="525ae-133">Если сборка со строгим именем помещается в глобальный кэш сборок, то имя файла сборки должно соответствовать имени сборки (без учета расширения файла — например EXE или DLL).</span><span class="sxs-lookup"><span data-stu-id="525ae-133">If you put a strong-named assembly in the global assembly cache, the assembly's file name must match the assembly name (not including the file name extension, such as .exe or .dll).</span></span> <span data-ttu-id="525ae-134">Так, если имя файла сборки — myAssembly.dll, то именем сборки должно быть myAssembly.</span><span class="sxs-lookup"><span data-stu-id="525ae-134">For example, if the file name of an assembly is myAssembly.dll, the assembly name must be myAssembly.</span></span> <span data-ttu-id="525ae-135">Имена закрытых сборок, развертываемых только в корневом каталоге приложения, могут отличаться от соответствующих файловых имен.</span><span class="sxs-lookup"><span data-stu-id="525ae-135">Private assemblies deployed only in the root application directory can have an assembly name that is different from the file name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="525ae-136">См. также</span><span class="sxs-lookup"><span data-stu-id="525ae-136">See Also</span></span>  
 <span data-ttu-id="525ae-137">[Практическое руководство. Определение полного имени сборки](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md) </span><span class="sxs-lookup"><span data-stu-id="525ae-137">[How to: Determine an Assembly's Fully Qualified Name](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md) </span></span>  
 <span data-ttu-id="525ae-138">[Создание сборок](../../../docs/framework/app-domains/create-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="525ae-138">[Creating Assemblies](../../../docs/framework/app-domains/create-assemblies.md) </span></span>  
 <span data-ttu-id="525ae-139">[Сборки со строгими именами](../../../docs/framework/app-domains/strong-named-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="525ae-139">[Strong-Named Assemblies](../../../docs/framework/app-domains/strong-named-assemblies.md) </span></span>  
 <span data-ttu-id="525ae-140">[Глобальный кэш сборок](../../../docs/framework/app-domains/gac.md) </span><span class="sxs-lookup"><span data-stu-id="525ae-140">[Global Assembly Cache](../../../docs/framework/app-domains/gac.md) </span></span>  
 <span data-ttu-id="525ae-141">[Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="525ae-141">[How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span></span>  
 [<span data-ttu-id="525ae-142">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="525ae-142">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
